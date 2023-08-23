FROM rust:latest
RUN apt-get update && apt-get install -y cmake pkg-config libssl-dev clang socat
RUN cargo install --git https://github.com/matter-labs/era-test-node.git --locked
COPY start_script.sh /start_script.sh
RUN chmod +x /start_script.sh
ENTRYPOINT ["/start_script.sh"]