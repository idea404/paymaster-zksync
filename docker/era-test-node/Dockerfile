# Use Ubuntu 18.04 as the base image with x86_64
FROM ubuntu:18.04@sha256:dca176c9663a7ba4c1f0e710986f5a25e672842963d95b960191e2d9f7185ebe
FROM rust:latest
RUN apt-get update && apt-get install -y cmake pkg-config libssl-dev clang socat
RUN cargo install --git https://github.com/matter-labs/era-test-node.git --locked
COPY start_script.sh /start_script.sh
RUN chmod +x /start_script.sh
ENTRYPOINT ["/start_script.sh"]