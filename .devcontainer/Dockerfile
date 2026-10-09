# Rust development container for VS Code Dev Containers
# Official Rust image (Debian Bookworm) with the latest stable Rust 1.x
FROM rust:1-bookworm

ARG USERNAME=dev
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Extra tools: lldb for debugging, sudo for installing things later
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       lldb \
       sudo \
       less \
       nano \
    && rm -rf /var/lib/apt/lists/*

# Rust components: formatter, linter, and std source (used by rust-analyzer)
RUN rustup component add rustfmt clippy rust-src

# Non-root user that matches a typical host UID so files you create are owned by you
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m -s /bin/bash $USERNAME \
    && echo "$USERNAME ALL=(root) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME \
    && mkdir -p /usr/local/cargo/registry \
    && chown -R $USERNAME:$USERNAME /usr/local/cargo /usr/local/rustup

USER $USERNAME
WORKDIR /workspace
