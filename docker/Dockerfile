FROM registry.fedoraproject.org/fedora:latest
MAINTAINER Julio Faracco <jcfaracco@gmail.com>

RUN dnf update -y

RUN dnf install -y \
        SDL2-devel \
        SDL2_image-devel \
        alsa-lib-devel \
        bash \
        bc \
        bison \
        brlapi-devel \
        bzip2 \
        bzip2-devel \
        ca-certificates \
        capstone-devel \
        ccache \
        clang \
        ctags \
        cyrus-sasl-devel \
        daxctl-devel \
        dbus-daemon \
        device-mapper-multipath-devel \
        diffutils \
        findutils \
        flex \
        fuse3-devel \
        gcc \
        gcc-c++ \
        gcovr \
        gettext \
        git \
        glib2-devel \
        glib2-static \
        glibc-langpack-en \
        glibc-static \
        glusterfs-api-devel \
        gnutls-devel \
        gtk3-devel \
        hostname \
        jemalloc-devel \
        json-c-devel \
        libaio-devel \
        libasan \
        libattr-devel \
        libbpf-devel \
        libcacard-devel \
        libcap-ng-devel \
        libcmocka-devel \
        libcurl-devel \
        libdrm-devel \
        libepoxy-devel \
        libfdt-devel \
        libffi-devel \
        libgcrypt-devel \
        libiscsi-devel \
        libjpeg-devel \
        libnfs-devel \
        libpmem-devel \
        libpng-devel \
        librbd-devel \
        libseccomp-devel \
        libselinux-devel \
        libslirp-devel \
        libssh-devel \
        libtasn1-devel \
        libubsan \
        liburing-devel \
        libusbx-devel \
        libxdp-devel \
        libzstd-devel \
        llvm \
        lttng-ust-devel \
        lzo-devel \
        make \
        mesa-libgbm-devel \
        meson \
        mtools \
        ncurses-devel \
        nettle-devel \
        ninja-build \
        nmap-ncat \
        numactl-devel \
        openssh-clients \
        pam-devel \
        pcre-static \
        pipewire-devel \
        pixman-devel \
        pkgconfig \
        pulseaudio-libs-devel \
        python3 \
        python3-PyYAML \
        python3-numpy \
        python3-opencv \
        python3-pillow \
        python3-pip \
        python3-sphinx \
        python3-sphinx_rtd_theme \
        rdma-core-devel \
        sed \
        snappy-devel \
        socat \
        sparse \
        spice-protocol \
        spice-server-devel \
        swtpm \
        systemd-devel \
        systemtap-sdt-devel \
        tar \
        tesseract \
        tesseract-langpack-eng \
        usbredir-devel \
        util-linux \
        vim \
        virglrenderer-devel \
        vte291-devel \
        which \
        xen-devel \
        xfsprogs-devel \
        xorriso \
        zlib-devel \
        zlib-static \
        zstd && \
    dnf autoremove -y && \
    dnf clean all -y

RUN git clone https://github.com/qemu/qemu.git -b v8.2.2 --depth 1

WORKDIR /qemu

RUN ./configure --target-list=x86_64-softmmu,x86_64-linux-user --disable-docs

RUN make install

WORKDIR /root

RUN rm -rf /qemu
