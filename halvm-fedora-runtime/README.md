HalVM on Fedora
===============

This Docker image contains a Fedora system with HalVM.
Based on [afdudley/halvm](https://registry.hub.docker.com/u/afdudley/halvm/) (which uses Arch Linux).

Github page: <https://github.com/stadlerb/halvm_fedora_docker>

See [the HalVM Github page](https://github.com/GaloisInc/HaLVM) for more details.


Note:
-----
By mistake, in version 0.1 the xen utilities are missing from halvm-fedora-base. As I didn't want to rebuild halvm-fedora-runtime, I added them manually to the halvm-fedora-runtime image. 

If you want to rebuild only halvm-fedora-runtime without building halvm-fedora-base first, please run: 

`docker run -t stadlerb/halvm-fedora-base:0.1 /bin/bash -c "yum install -y xen && yum clean all"`

After this, `docker ps -a` will give you a line like this:

`cb30744fe734	stadlerb/halvm-fedora-base:0.1	"/bin/bash -c 'yum i	About a minute ago	Exited (0) 5 seconds ago	mad_cori`

Use the hash in the beginning to create a new local image of halvm-fedora-base: 

`docker commit cb30744fe734 stadlerb/halvm-fedora-base`

After that, you can run `make` in halvm-fedora-runtime.