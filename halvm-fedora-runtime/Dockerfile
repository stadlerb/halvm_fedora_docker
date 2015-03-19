FROM stadlerb/halvm-fedora-base

# Clone 'master' of HaLVM and build it.

MAINTAINER Bernhard Stadler <Bernhard-Stadler@gmx.net>

USER root

WORKDIR /build
RUN git clone https://github.com/GaloisInc/HaLVM.git\
    && cd /build/HaLVM\
    && git submodule update --init --recursive\
    && autoconf\
    && ./configure --prefix=/opt/halvm --enable-gmp\
    && make\
    && make install\
    && cd /build\
    && rm -rf /build/HaLVM\
    && cabal update\
    ; true

WORKDIR /build
CMD /usr/bin/bash
