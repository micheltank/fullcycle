FROM golang:1.15.5-alpine AS builder

ENV GOPATH="$HOME/go"
WORKDIR $GOPATH/src/github.com/micheltank/challenge
COPY . $GOPATH/src/github.com/micheltank/challenge
RUN go build

FROM scratch

ENV GOPATH="$HOME/go"
WORKDIR /app
COPY --from=builder $GOPATH/src/github.com/micheltank/challenge .

ENTRYPOINT ["./challenge"]