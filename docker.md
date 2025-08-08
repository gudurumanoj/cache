## Docker

to get the docker digests: `docker images --digests`

```bash
docker run -it  --rm --network host   --name <name>   --shm-size 10.24g   --gpus all -e HUGGING_FACE_HUB_TOKEN=<HF_TOKEN>  -v <vol_on_disk>:<vol_on_docker>   -v <vol_on_disk>:<vol_on_docker>   --entrypoint /bin/bash   vllm/vllm-openai:v0.8.4


docker run -it  --rm --network host   --shm-size 10.24g   --gpus all -e HUGGING_FACE_HUB_TOKEN=<HF_TOKEN>   -v <vol_on_disk>:<vol_on_docker>   -v <vol_on_disk>:<vol_on_docker>   --entrypoint /bin/bash   vllm/vllm-openai:v0.8.5.post1


docker run --rm --network=host --privileged --gpus all -it --rm --ipc=host --shm-size=24g -v <vol_on_disk>:<vol_on_docker>   -v <vol_on_disk>:<vol_on_docker> <docker_name>
```

```bash
docker pull vllm/vllm-openai:v0.8.4
```
