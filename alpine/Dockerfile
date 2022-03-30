FROM alpine:3.15

ENV OP_VERSION 2.0.0
RUN apk add --no-cache ca-certificates \
    && apk add --no-cache --virtual .build-deps gnupg \
    && cd /root \
    && wget -O op.zip https://cache.agilebits.com/dist/1P/op2/pkg/v$OP_VERSION/op_linux_arm64_v$OP_VERSION.zip \
    && unzip op.zip \
    && gpg --receive-keys 3FEF9748469ADBE15DA7CA80AC2D62742012EA22 \
    && gpg --verify op.sig op \
    && mv op /usr/local/bin \
    && rm -rf .[!.]* * \
    && apk del .build-deps

ENTRYPOINT ["op"]
