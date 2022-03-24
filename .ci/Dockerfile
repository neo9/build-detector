FROM alpine:latest

RUN apk add --no-cache bash jq
ADD ./build-detector /usr/local/bin

WORKDIR /data
ENTRYPOINT ["/usr/local/bin/build-detector"]
