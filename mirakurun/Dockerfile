FROM chinachu/mirakurun:latest

RUN apt purge -y pcscd

# recpt1
RUN apt-get update && \
    apt-get install -y --no-install-recommends \
        build-essential \
        libtool \
        autoconf \
        git \
        automake &&\
    git clone https://github.com/stz2012/recpt1 /tmp/recpt1 && \
    cd /tmp/recpt1/recpt1 && \
    ./autogen.sh && \
    ./configure && \
    make && \
    make install && \
    rm -rf /tmp/recpt1 && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

COPY libpcsclite.so.1.0.0 /usr/lib/x86_64-linux-gnu/libpcsclite.so.1.0.0
