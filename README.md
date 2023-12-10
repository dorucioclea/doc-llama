## Docker Containers for a local OPEN AI compatible API

Open AI API compatible docker images. We select models and package them in high performance docker containers.

|Image Name   |Parameters   | Type  | Context Size  | Image Size  | Quantization  | Ram Requirements  |
|---|---|---|---|---|---|---|
|llama-2-7b-chat:1.0.4| 7b  | LLama 2  | 2K | 5GB  | Yes  | 16GB  |

## Features

- API implements batching meaning when multiple users make a request the API serves them in parallel.
- The docker image contains the model, no needs to download the model in another step.
- Images are optimized for different architectures [coming soon]

## Startup the API

```sh
docker run -it --rm -p 3000:3000 ghcr.io/bionic-gpt/llama-2-7b-chat:1.0.4
```

## Try it out

```sh
curl http://localhost:3000/v1/chat/completions -H "Content-Type: application/json" -d '{
     "model": "llama2-chat", 
     "messages": [{"role": "user", "content": "How are you?"}],
     "temperature": 0.1 
   }'
```