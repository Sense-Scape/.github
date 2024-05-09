# Building With Docker

- Install Docker
- sudo apt-get install qemu-user-static -> Allows for cross architectural compilation
- Specify base os to align with system one whishes to develop on - this includes architecture and glibc version
- eg: docker buildx build --platform linux/arm64 -t my-arm-image . -> Creates the docker with which to build the specified architecture
- Interactively bring up the container: docker run --platform linux/arm64 -it --name my-container my-arm-image
- Verify architecture using uname -m
