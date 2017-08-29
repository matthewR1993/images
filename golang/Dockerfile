FROM golang:latest

ENV REPO github.com/matthewR1993/services

ADD . /go/src/$REPO

WORKDIR /go/src/$REPO

ENV PATH /go/src/$REPO:$PATH

EXPOSE 8080

RUN make build
RUN chmod +x build_file_name

CMD build_file_name
