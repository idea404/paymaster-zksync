# Use Ubuntu 18.04 as the base image
FROM ubuntu:18.04

# Install necessary dependencies
RUN apt-get update && apt-get install -y wget cmake pkg-config libssl-dev clang socat

# Fetch and extract the era_test_node binary
RUN wget https://github.com/matter-labs/era-test-node/releases/download/v0.1.0/era_test_node-v0.1.0-x86_64-unknown-linux-gnu.tar.gz \
    && tar -xzf era_test_node-v0.1.0-x86_64-unknown-linux-gnu.tar.gz \
    && mv era_test_node /usr/local/bin/ \
    && rm era_test_node-v0.1.0-x86_64-unknown-linux-gnu.tar.gz

# Copy the start script
COPY start_script.sh /start_script.sh

# Make the start script executable
RUN chmod +x /start_script.sh

# Set the start script as the entry point
ENTRYPOINT ["/start_script.sh"]
