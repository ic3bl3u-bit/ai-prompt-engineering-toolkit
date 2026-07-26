# RTX 3090 + Qwen 3.6-35B-A3B: 170 tok/s Configuration
# ============================================================
# Benchmark: 170 tok/s (code), 125 tok/s (creative), $0 per token
# Hardware: RTX 3090 24GB | Intel i9-10900K | 24GB RAM (upgrade to 48GB+)
# Software: llama.cpp b9971 (turboquant) | CUDA 12.9 | WSL2 Ubuntu 26.04
#
# Full tuning diary: https://medium.com/@ic3bl3u/how-i-pushed-an-rtx-3090-to-170-tokens-per-second-with-qwen-3-6-35b-a88079616d07
# Technical reference: https://ic3bl3u-bit.github.io/ai-prompt-engineering-toolkit/blog/rtx-3090-170-tokens-per-second/

# ============================================================
# 1. BUILD COMMAND (architecture-specific for Ampere / compute 8.6)
# ============================================================

cmake -B build \
  -DGGML_CUDA=ON \
  -DCMAKE_CUDA_ARCHITECTURES=86 \
  -DGGML_CUDA_FA_ALL_QUANTS=ON \
  -DGGML_NATIVE=ON \
  -DGGML_LTO=ON \
  -DGGML_CUDA_GRAPHS=ON \
  -DGGML_CUDA_F16=ON

cmake --build build --config Release -j 10

# ============================================================
# 2. SERVER LAUNCH COMMAND (the main config)
# ============================================================

llama-server --port ${PORT} \
  --model Qwen3.6-35B-A3B-UD-IQ4_XS.gguf \
  --mmproj mmproj-F16.gguf \
  -c 131072 -ngl 99 -fa on -b 1024 -ub 2048 \
  -t 10 -tb 16 \
  --cache-type-k q8_0 --cache-type-v turbo4 \
  -fit off --no-mmap --mlock --jinja \
  --poll 100 --prio 2 --reasoning off \
  -np 1 \
  --spec-type draft-mtp --spec-draft-n-max 2

# ============================================================
# 3. FLAG REFERENCE
# ============================================================

# -ngl 99                    All layers on GPU (no CPU offload)
# -fa on                     Flash Attention (non-negotiable for Ampere)
# -c 131072                  Context window (reduce to 65536 if < 48GB RAM!)
# -b 1024                    Batch size for 24GB VRAM budget
# -ub 2048                   Prompt processing chunk size
# -t 10                      CPU threads (match physical cores)
# --cache-type-k q8_0        Quantized K cache (saves VRAM)
# --cache-type-v turbo4      TurboQuant V cache (best speed/quality)
# --no-mmap                  Eliminates page-fault jitter
# --mlock                    Locks model in RAM (needs 48GB+ RAM)
# --jinja                    Jinja2 chat templates (for agent frameworks)
# --reasoning off            Disable thinking blocks (saves tokens)
# --spec-type draft-mtp      MTP speculative decoding (+21% on code)
# --spec-draft-n-max 2       2-token draft window (91% acceptance)

# ============================================================
# 4. MTP BENCHMARKS BY WORKLOAD
# ============================================================

# Code generation:    126.7 -> 169.7 tok/s (+21%, 91% acceptance)
# Creative writing:   126.7 -> 125.3 tok/s (-1%, 62% acceptance)
# Short responses:    ~120  -> 57.7 tok/s  (-52%, setup overhead)

# ============================================================
# 5. SAMPLING PARAMS (agent workloads)
# ============================================================

# temperature: 0.6           (0.3 causes repetitive loops on multi-step)
# top_p: 0.95                (wider pool for format compliance)
# top_k: 20                  (bounds candidate pool)
# repetition_penalty: 1.05

# ============================================================
# 6. OOM CRASH WARNING
# ============================================================

# If you have < 48GB RAM, DO NOT use -c 131072 + --mlock together.
# The KV cache (4-6GB) + model weights (17-18GB) + --mlock pinning
# = OOM killer. Use -c 65536 for default, or drop --mlock.
#
# Monitor with: watch -n1 'cat /proc/$(pidof llama-server)/status | grep VmRSS'

# ============================================================
# 7. BENCHMARK COMPARISON (vs published results)
# ============================================================

# This setup:          IQ4_XS + MTP    169.7 tok/s   <- YOU ARE HERE
# Japanese (zephel01): IQ4_NL          149.8 tok/s
# Giles Thomas:        UD-IQ4_NL_XL    140.0 tok/s
# HN (thc1006):        UD-Q4_K_XL      135.7 tok/s
# HF Discussion:       UD-Q3_K_M       120.0 tok/s
# Reddit r/LocalLLaMA: unspecified     113.0 tok/s
