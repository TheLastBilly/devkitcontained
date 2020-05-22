FROM debian:buster-slim

LABEL maintainer="Jose Ricardo jtmonegro@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && \
    apt install -y apt-utils && \
    apt install -y --no-install-recommends sudo ca-certificates pkg-config curl wget bzip2 xz-utils make git bsdtar doxygen gnupg vim fish && \
    apt clean

RUN wget https://github.com/devkitPro/pacman/releases/latest/download/devkitpro-pacman.deb && \
    dpkg -i devkitpro-pacman.deb && \
    rm devkitpro-pacman.deb && \
    dkp-pacman -Scc --noconfirm

ENV DEVKITPRO=/opt/devkitpro
ENV PATH=${DEVKITPRO}/tools/bin:$PATH