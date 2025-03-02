FROM golang:1.21.1 AS builder

WORKDIR /app

COPY . .
RUN go mod download
RUN CGO_ENABLED=0 GOOS=linux go build -o auth-api .

FROM alpine:latest  
RUN apk --no-cache add ca-certificates
WORKDIR /root/
COPY --from=builder /app/auth-api .
EXPOSE 8081
CMD ["./auth-api"]