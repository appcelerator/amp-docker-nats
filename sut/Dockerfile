From appcelerator/alpine:20160726
ENV GOPATH          /go
ENV GOBIN           /go/bin
RUN apk update && apk upgrade && \
    apk add go>1.6 git && \
    go get -v github.com/nats-io/nats && \
    cd $GOPATH/src/github.com/nats-io/nats && \
    cp examples/*.go /bin/
RUN cd $GOPATH/src/github.com/nats-io/nats/examples && \
    mkdir $GOBIN && \
    go install nats-pub.go

COPY ./test.sh /bin
CMD ["/bin/test.sh"]
