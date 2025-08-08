## vllm

```bash
vllm serve Qwen/Qwen3-32B --served-model-name qwen --enable-reasoning --reasoning-parser deepseek_r1 --tensor-parallel-size 8 --max_model_len 8192 --load-format auto --dtype bfloat16 --host 0.0.0.0 --port 8000 --generation-config auto --override-generation-config '{"top_k": 50}'

vllm serve google/gemma-3-27b-it --served-model-name gemma3 --dtype bfloat16 --tensor-parallel-size 8 --gpu-memory-utilization 0.9 --max-model-len 8192 --load-format auto --host 0.0.0.0
 --port 8000 --generation-config auto --override-generation-config '{"top_k": 50}'


vllm serve /path/to/hf_cache/hub/models--<model_name>/snapshots/<some_hash> --served-model-name <model_name> --dtype bfloat16 --tensor-parallel-size 8 --gpu-memory-utilization 0.9 --max-model-len 16384 --load-format auto --host 0.0.0.0 --port 8000 --generation-config auto 



NCCL_NVLS_ENABLE=0 vllm serve <model_name>  --served-model-name qwen --enable-reasoning --reasoning-parser deepseek_r1 --tensor-parallel-size 8 --max_model_len 16384 --load-format auto --dtype bfloat16 --host 0.0.0.0 --port 8111 --generation-config auto    ## that flag somehow seems to be helping in moving vllm hosting past the using vllm version==0.21.5 
```




```bash
pip install  tokenizers==0.21.0;export VLLM_RPC_TIMEOUT=100000;vllm serve ...
```


`export VLLM_WORKER_MULTIPROC_METHOD=spawn    ## for some unable to spawn debug`
`export VLLM_RPC_TIMEOUT=100000`             ## watchdog timeout
`NCCL_NVLS_ENABLE=0`                       ## don't know what this does internally but seems to be working

For less cards, use `CUDA_VISIBLE_DEVICES=0,1,2,3` and make `tensor-parallel-size` as 4 etc
