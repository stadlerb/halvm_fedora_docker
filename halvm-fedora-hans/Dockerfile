FROM stadlerb/halvm-fedora-runtime

# Compile install the HaNS from github.

MAINTAINER Bernhard Stadler <Bernhard-Stadler@gmx.net>

USER root

# Install HaNS
WORKDIR /build
RUN git clone https://github.com/GaloisInc/HaNS.git\
    && cd /build/HaNS\
    && halvm-cabal -j1 install


WORKDIR /build
CMD /usr/bin/bash
