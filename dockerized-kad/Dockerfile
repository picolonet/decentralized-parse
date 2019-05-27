FROM golang:1.12.5

WORKDIR $GOPATH/src/github.com/kaushikc92/chat

COPY ./flags.go .
COPY ./chat.go .
COPY ./go.mod .

ENV GO111MODULE=on

RUN go build -o ./chat .

ARG PORT_NO
ENV PORT_NO=${PORT_NO}
CMD ./chat -listen /ip4/127.0.0.1/tcp/${PORT_NO}
