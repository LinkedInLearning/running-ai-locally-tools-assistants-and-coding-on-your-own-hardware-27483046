## running qwen
```bash
LLAMA_ARG_PORT=8881 ./bin/llama-server \
    -m ~/.cache/huggingface/hub/models--unsloth--Qwen3.6-35B-A3B-GGUF/snapshots/*/Qwen3.6-35B-A3B-UD-Q4_K_XL.gguf  
  \
    --mmproj ~/.cache/huggingface/hub/models--unsloth--Qwen3.6-35B-A3B-GGUF/snapshots/*/mmproj-F16.gguf \
    --alias unsloth/Qwen3.6-35B-A3B -ngl 99 -c 32768 -fa on \
    --host 0.0.0.0 --jinja --reasoning-format deepseek \
    --temp 0.6 --top-p 0.95 --top-k 20 --min-p 0.0 \
    > ~/qwen36-35b.log 2>&1 & echo "pid $!"
```
