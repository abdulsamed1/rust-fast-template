FROM rust:1.81-bullseye

# Install system tools and LLVM 19
RUN apt-get update && apt-get install -y \
    clang-19 lld-19 lldb-19 \
    pkg-config libssl-dev \
    && rm -rf /var/lib/apt/lists/*

# Install useful cargo tools
RUN cargo install cargo-watch cargo-edit

WORKDIR /workspace

# Default command: open a shell
CMD ["/bin/bash"]
