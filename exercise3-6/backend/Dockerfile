FROM golang:1.16-alpine3.15 AS build-stage

WORKDIR /usr/src/app
COPY . .

RUN go build

FROM alpine:3.15.4

EXPOSE 8080
WORKDIR /usr/src/app

COPY --from=build-stage /usr/src/app/server /usr/src/app/

ENV REDIS_HOST=redis
ENV REQUEST_ORIGIN=http://localhost:5001

CMD ["./server"]
