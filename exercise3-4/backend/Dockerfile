FROM golang:1.16

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build && rm -rf /var/lib/apt/lists/* && useradd -m appuser && rm -rf /go

ENV REDIS_HOST=redis
ENV REQUEST_ORIGIN=http://localhost:5001

USER appuser

CMD ["./server"]
