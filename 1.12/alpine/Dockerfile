FROM golang:1.12.4-alpine

RUN apk add --no-cache git && \
    go get github.com/pilu/fresh

ENV WORKDIR .

CMD [ "fresh", "${GOPATH}/src/${WORKDIR}" ]
