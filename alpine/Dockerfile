FROM alpine:3.10

ENV OP_VERSION 0.6.1
RUN apk add --no-cache ca-certificates \
    && apk add --no-cache --virtual .build-deps gnupg \
    && cd /root \
    && wget -O op.zip https://cache.agilebits.com/dist/1P/op/pkg/v$OP_VERSION/op_linux_386_v$OP_VERSION.zip \
    && unzip op.zip \
    && gpg --receive-keys 3FEF9748469ADBE15DA7CA80AC2D62742012EA22 \
    && gpg --verify op.sig op \
    && mv op /usr/local/bin \
    && rm -rf .[!.]* * \
    && apk del .build-deps

ENTRYPOINT ["op"]
