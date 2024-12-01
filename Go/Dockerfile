# Use the official Go image for building
FROM golang:1.21 AS build

# Set the working directory inside the container
WORKDIR /app

# Copy the Go module files and download dependencies
COPY go.mod go.sum ./
RUN go mod download

# Copy the application code
COPY . .

# Build the application
RUN go build -o main .

# Use a minimal base image for running the app
FROM debian:bullseye-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the compiled binary from the build stage
COPY --from=build /app/main .

# Expose the port your Go app listens on
EXPOSE 8080

# Run the Go app
CMD ["./main"]
