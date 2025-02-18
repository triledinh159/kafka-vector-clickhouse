FROM alpine:latest

# Install dependencies and Vector
RUN apk add --no-cache curl bash && \
    curl --proto '=https' --tlsv1.2 -sSfL https://sh.vector.dev | bash -s -- -y --prefix /usr/local

# Create the /etc/vector directory inside the container
RUN mkdir -p /etc/vector

# Set Vector as the default entrypoint
ENTRYPOINT ["/usr/local/bin/vector"]

# Default command to run Vector with an external config
CMD ["--config", "/etc/vector/vector.yaml"]
