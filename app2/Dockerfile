# Use the official Golang image to create a binary
FROM golang:1.19 as builder
WORKDIR /app

# Copy go.mod and go.sum first to leverage Docker layer caching
COPY go.mod .
# Download dependencies
RUN go mod download

# Copy the code into the container
COPY . .

# Build the Go app
RUN go build -o hello-app2

# Use a minimal base image
FROM alpine:latest
WORKDIR /root/

# Copy the compiled binary from builder
COPY --from=builder /app/hello-app2 .

# Run the compiled binary
CMD ["./hello-app2"]



