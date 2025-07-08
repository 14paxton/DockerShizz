# DockerShizz

```shell
DOCKER_BUILDKIT=1 docker buildx build --platform=linux/arm64 --build-arg BUILDKIT_INLINE_CACHE=1 -t graalpy-venv -f Dockerfile.graalpy-build .
```
# inspect image
```shell
docker buildx imagetools inspect ghcr.io/graalvm/graalpy-community:24
```
```shell
docker buildx imagetools inspect  container-registry.oracle.com/graalvm/graalpy
```
```shell
docker buildx imagetools inspect container-registry.oracle.com/graalvm/native-image:24-muslib
```
```shell
docker buildx imagetools inspect container-registry.oracle.com/graalvm/native-image
```
```shell
docker buildx imagetools inspect ghcr.io/graalvm/graalvm-community
```

# run image to check
```shell
docker run --rm -it --entrypoint /bin/sh --platform=linux/arm64 container-registry.oracle.com/graalvm/native-image:24-muslib
```

```shell
docker run --rm -it --entrypoint /bin/sh container-registry.oracle.com/graalvm/graalvm-community:latest
```

```shell
docker run --rm -it --entrypoint /bin/sh  --platform=linux/arm64 ghcr.io/graalvm/graalvm-community
```

```shell
docker run --rm -it --entrypoint /bin/sh  ghcr.io/graalvm/graalpy-community
```

```shell
docker build --target builder -t graalpy-pandas .
docker create --name graalpy-pandas-container graalpy-pandas
docker cp graalpy-pandas-container:/resources ./dist
docker rm graalpy-pandas-container
```


```shell
git clone https://github.com/PaddlePaddle/Paddle.git

cd pandas

git checkout tags/v2.2.3 -b v2.2.3-branch        

python3 -m venv build-env   

source build-env/bin/activate  

pip install --upgrade pip    

pip install build setuptools wheel delocate 

python -m build     

delocate-wheel dist/*.whl    
```




