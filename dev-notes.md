## Tests
###
    lm_eval --model local-chat-completions --model_args "base_url=http://localhost:8192/v1/chat/completions,tokenized_requests=False" --tasks gsm8k --apply_chat_template --fewshot_as_multiturn --num_fewshot 5 --limit 20

###
    vllm bench serve --model Qwen/Qwen3-0.6B --num-prompts 1000 --port 8192 --random-input-len 16 --seed $(date +%s)

## Deployment
### Dockerfile
    Dockerfile.kv
    DOCKER_BUILDKIT=1 docker build --build-arg GITHUB_TOKEN=$(cat ~/.github_token) -t llm-d/nixl_kv_layout . -f Dockerfile.kv_1 --load

### POD yaml
    pok-deployment-new-2.yaml
