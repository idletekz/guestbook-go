FROM golang:alpine as builder
# Git is required for fetching the dependencies.
RUN apk update && apk add --no-cache git
RUN mkdir /app && apk update && apk add git
ADD main.go go.mod go.sum /app/
ADD static /app/static
WORKDIR /app
RUN CGO_ENABLED=0 GOOS=linux go build -o main .

FROM scratch
WORKDIR /app
COPY --from=builder /app/main .
CMD ["/app/main"]
EXPOSE 3000