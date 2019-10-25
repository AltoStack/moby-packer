# Moby Packer

Packer CLI in a Docker image.

## Usage

### Docker Command

```shell script
docker run --rm -it -v ~/.aws:/root/.aws -v $(pwd):/opt/app --entrypoint bash altostack/packer 
```

### Docker Compose

```yaml
packer:
  image: altostack/packer
  env_file: .env
  working_dir: /opt/app
  entrypoint: packer
  volumes:
    - .:/opt/app:rw
    - ${SSH_AUTH_SOCK}:${SSH_AUTH_SOCK}
```

## Build

Update the `TERRAFORM_VERSION` in both `Makefile` and `DockerFile`. Then run:

```shell script
make build
```
