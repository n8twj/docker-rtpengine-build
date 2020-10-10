FROM debian:buster

ENV DEBIAN_FRONTEND noninteractive
ENV RTPENGINE_VERSION mr9.0.1.2
ENV DEB_BUILD_PROFILES pkg.ngcp-rtpengine.nobcg729

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git \
    dpkg-dev \
    cmake \
    unzip \
    wget \
    debhelper-compat \
    default-libmysqlclient-dev \
    gperf \
    iptables-dev \
    libavcodec-dev \
    libavfilter-dev \
    libavformat-dev \
    libavutil-dev \
    libbencode-perl \
    libcrypt-openssl-rsa-perl \
    libcrypt-rijndael-perl \
    libcurl4-openssl-dev \
    libdigest-crc-perl \
    libdigest-hmac-perl \
    libevent-dev libglib2.0-dev \
    libhiredis-dev libio-multiplex-perl \
    libio-socket-inet6-perl libiptc-dev \
    libjson-glib-dev libnet-interface-perl \
    libpcap0.8-dev \
    libpcre3-dev \
    libsocket6-perl \
    libspandsp-dev \
    libssl-dev \
    libswresample-dev \
    libsystemd-dev \
    libxmlrpc-core-c3-dev \
    markdown \
    curl \
    wget \
    zlib1g-dev && \
    cd /usr/src && \
    git clone -b $RTPENGINE_VERSION https://github.com/sipwise/rtpengine.git && \
    cd rtpengine && \
    dpkg-buildpackage && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /opt/deb && \
    mv /usr/src/*.deb /opt/deb

VOLUME ["/opt/deb"]