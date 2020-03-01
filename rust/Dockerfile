FROM rust:{RUST_VERSION}{DOCKER_TYPE}
RUN rustup toolchain uninstall $(rustup default)
RUN rustup toolchain install {RUST_TOOLCHAIN}
RUN rustup default {RUST_TOOLCHAIN}
RUN cargo install watchexec 
RUN rustup component add rustfmt
WORKDIR /var/www
EXPOSE 3001
RUN groupadd -g 61000 ferris 
RUN useradd -g 61000 -l -M -s /bin/false -u 61000 ferris 
RUN mkdir -p /usr/local/cargo/git; chown -R  ferris:ferris /usr/local/cargo
RUN mkdir -p /var/www; chown -R ferris:ferris /var/www
USER ferris

