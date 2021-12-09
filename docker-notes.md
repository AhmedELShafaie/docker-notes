To install docker buildx plugin
Use https://docs.docker.com/buildx/working-with-buildx/
wget -o ~/.docker/cli-plugins/docker-buildx https://github.com/docker/buildx/releases/download/v0.7.1/buildx-v0.7.1.linux-amd64
chmod a+x ~/.docker/cli-plugins/docker-buildx
docker buildx version 


To Build Mult-Architecure amdd64 || arm64
use https://docs.docker.com/desktop/multi-arch/
#https://stackoverflow.com/questions/69195158/docker-buildx-no-such-file-or-directory-on-arm64-platform
# Init
docker run --rm --privileged multiarch/qemu-user-static --reset -p yes

# Create a builder
docker buildx create --name mybuilder --driver docker-container

# Switch to builder and checkout
docker buildx use mybuilder
docker buildx inspect --bootstrap




