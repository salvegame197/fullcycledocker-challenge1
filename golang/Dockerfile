FROM golang:1.15-alpine3.13 as Builder

WORKDIR /src/app

COPY hello.go .

RUN go build -o /bin/project

FROM scratch

COPY --from=Builder /bin/project /project

ENTRYPOINT ["/project"]

CMD ["--help"]