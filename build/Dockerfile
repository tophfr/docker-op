FROM debian:buster-slim

ENV OP_VERSION 0.9.1
RUN buildDeps="curl gnupg dirmngr unzip" \
    && runDeps="ca-certificates" \
    && apt-get update \
    && apt-get install -y --no-install-recommends $runDeps $buildDeps \
    && cd /root \
    && curl -sSL -o op.zip https://cache.agilebits.com/dist/1P/op/pkg/v$OP_VERSION/op_linux_amd64_v$OP_VERSION.zip \
    && unzip op.zip \
    && gpg --keyserver hkp://keyserver.ubuntu.com --receive-keys 3FEF9748469ADBE15DA7CA80AC2D62742012EA22 \
    && gpg --verify op.sig op \
    && mv op /usr/local/bin \
    && rm -Rf * .gnupg \
    && apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false -o APT::AutoRemove::SuggestsImportant=false $buildDeps \
    && rm -r /var/lib/apt/lists/*

ENTRYPOINT ["op"]
