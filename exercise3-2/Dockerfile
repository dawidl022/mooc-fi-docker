FROM alpine:3.15.4

RUN apk add bash git docker-cli

WORKDIR /usr/src/app
COPY ./build ./
RUN chmod +x ./build

ENTRYPOINT [ "./build" ]
