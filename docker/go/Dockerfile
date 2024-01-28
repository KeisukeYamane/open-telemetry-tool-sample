FROM golang:1.20-alpine

WORKDIR /app

RUN apk upgrade --update && \
   apk --no-cache add git protobuf bash && \
   go install github.com/cosmtrek/air@latest

COPY go.mod go.sum ./
COPY ./go.mod ./
RUN go mod download

CMD ["air", "-c", ".air.toml"]