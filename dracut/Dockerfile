# sudo docker run -it --privileged -v $PWD:/data -v /lib/modules:/lib/modules ubuntu /bin/bash

FROM ubuntu

RUN apt update
RUN apt install git-core -y
RUN git clone https://github.com/dracutdevs/dracut
WORKDIR dracut/
RUN git checkout 057
RUN apt install \
    build-essential \
    pkg-config \
    libkmod-dev \
    asciidoc \
    iproute2 \
    ntfs-3g \
    curl \
    libsystemd-dev \
    squashfs-tools \
    udev \
    kmod \
    network-manager \
    zstd \
    systemd-coredump  \
    dbus-broker \
    rpcbind \
    btrfs-progs \
    cpio -y
RUN ./configure
RUN make
RUN make install
# RUN cp -r /data/dracut/modules.d .
# RUN cp -r /data/dracut/usr/bin/ /usr
# RUN cp -r /data/dracut/usr/libexec/ /usr
RUN dracut \
    --verbose \
    --no-hostonly \
    --add "\
    bash \
    systemd \
    systemd-coredump \
    systemd-initrd \
    systemd-journald \
    systemd-modules-load \
    systemd-sysctl \
    systemd-tmpfiles \
    systemd-udevd \
    network \
    network-manager \
    rescue \
    kernel-modules \
    kernel-network-modules \
    livenet \
    qemu-net \
    qemu \
    lunmask \
    udev-rules \
    dracut-systemd \
    base \
    dbus \
    dbus-daemon \
    ifcfg \
    dmsquash-live \
    ignition \
    " \
    --zstd \
    -f \
    /data/dracut/build/initrd.img
# cp initrd.img /var/mnt/out
