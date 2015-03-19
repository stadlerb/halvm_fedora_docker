
Fedora HaLVM Installation in a Docker Container
==================================================

Build scripts for a docker container with an HaLVM installation hosted
based on Fedora.

It is split into three sub-images (and corresponding directories),
which build upon each other:
1. halvm-fedora-base: A base system with all dependencies but without HalVM
2. halvm-fedora-runtime: HalVM runtime
3. halvm-fedora-hans: HaNS installation

halvm-fedora-runtime depends on halvm-fedora-base and halvm-fedora-hans
depends on halvm-fedora-runtime.
When rebuilding, it is possible to skip halvm-fedora-base or
halvm-fedora-runtime. Docker will then pull the public image from Docker Hub.

Usage
-----

1. Change into the directory of the image you want to build 
2. Run 'make'
