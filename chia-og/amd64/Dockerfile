FROM amd64/alpine:latest

ENV RELEASE_VERSION=1.5.5
ENV MINOR_VERSION=2


RUN cd /root \
    &&  wget --no-check-certificate -c https://github.com/hpool-dev/chia-miner/releases/download/${RELEASE_VERSION}/HPool-Miner-chia-og-v${RELEASE_VERSION}-${MINOR_VERSION}-linux.zip \
    &&  unzip HPool-Miner-chia-og-v${RELEASE_VERSION}-${MINOR_VERSION}-linux.zip -d HPool-Miner-chia-og \
    &&  cd HPool-Miner-chia-og/linux \
    &&  cp hpool-miner-chia-linux-amd64 /usr/bin/hpool-miner-chia-linux-amd64-og \
    &&  mkdir -p /etc/hpool-miner \
    &&  mkdir -p /var/log/hpool-miner \
    &&  mkdir -p /plots \
    &&  cp config.yaml /etc/hpool-miner/chia-og.yaml \
    &&  cd /root \
    &&  rm HPool-Miner-chia-og-v${RELEASE_VERSION}-${MINOR_VERSION}-linux.zip \
    &&  rm -rf HPool-Miner-chia-og/ 

ENTRYPOINT /usr/bin/hpool-miner-chia-linux-amd64-og -config /etc/hpool-miner/chia-og.yaml