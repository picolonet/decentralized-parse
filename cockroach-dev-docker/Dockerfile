FROM ubuntu:16.04

RUN apt-get update -y
RUN apt-get install -y vim wget git build-essential cmake autoconf bison curl apt-transport-https libncurses-dev

RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add -
RUN echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list

RUN apt-get update -y
RUN apt-get install -y yarn

RUN curl -sL https://deb.nodesource.com/setup_10.x | bash -
RUN apt-get install -y nodejs

RUN wget https://dl.google.com/go/go1.12.5.linux-amd64.tar.gz
RUN tar -C /usr/local -xzf go1.12.5.linux-amd64.tar.gz

ENV GOPATH /go
ENV PATH $GOPATH/bin:/usr/local/go/bin:$PATH

RUN go get github.com/derekparker/delve/cmd/dlv

RUN mkdir -p $(go env GOPATH)/src/github.com/cockroachdb
WORKDIR /go/src/github.com/cockroachdb
RUN git clone https://github.com/cockroachdb/cockroach
WORKDIR /go/src/github.com/cockroachdb/cockroach
RUN make build

CMD ["sh", "-c", "/bin/bash"]
