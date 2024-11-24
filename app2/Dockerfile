FROM golang:1.19
WORKDIR /app
# Copy go.mod and go.sum first to leverage Docker layer caching
COPY go.mod .
# Download dependencies
RUN go mod download
COPY main.go .
RUN go build -o app2 .
CMD ["./app2"]

