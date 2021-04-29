FROM golang:1.15-alpine3.13 as Builder

WORKDIR /src/app

COPY hello.go .

RUN GOOS=linux;go build -ldflags "-w"  hello.go

FROM scratch

COPY --from=Builder /src/app/hello /project

ENTRYPOINT ["/project"]
