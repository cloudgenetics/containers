# Scanpy 
> Version 1.7.2

## Docker build command

```
aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/csgenetics
docker buildx build --platform linux/amd64 . -t scanpy:1.7.2
docker tag scanpy:1.7.2 public.ecr.aws/csgenetics/scanpy:1.7.2
docker push public.ecr.aws/csgenetics/scanpy:1.7.2
```