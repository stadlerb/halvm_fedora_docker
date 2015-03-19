FROM fedora:21
MAINTAINER Bernhard Stadler <Bernhard-Stadler@gmx.net>
USER root

# Reinstall glibc because setting the UTF-8 locale won't work in the Fedora 21 image without this
RUN yum -y upgrade\
     ; yum -y reinstall glibc glibc-common

ENV HOME=/build\
    PATH=/opt/halvm/bin:/build/.cabal/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin\
    LANG=en_US.UTF-8\
    LC_ALL=en_US.UTF-8
ADD TO_INSTALL /TO_INSTALL
RUN export LANG=en_US.UTF-8\
     ; export LC_ALL=en_US.UTF-8\
     ; mkdir /build\
     && cat /TO_INSTALL | xargs yum -y install\
     && yum clean all
WORKDIR /build
CMD /usr/bin/bash