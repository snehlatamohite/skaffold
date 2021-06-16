FROM golang:1.12.5-alpine3.9 as builder
COPY web.go .
RUN export GOARCH=ppc64le && export GO111MODULE=auto && export CGO_ENABLED=0 && go build -o /web .

FROM alpine:3.9
CMD ["./web"]
COPY --from=builder /web .
