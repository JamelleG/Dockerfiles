FROM rust:{RUST_VERSION}
RUN rustup toolchain uninstall stable
RUN rustup toolchain install {RUST_TOOLCHAIN} && rustup component add --toolchain {RUST_TOOLCHAIN} rustfmt
RUN cargo install watchexec 
WORKDIR /var/www
EXPOSE 3001
RUN groupadd -g 61000 ferris 
RUN useradd -g 61000 -l -M -s /bin/false -u 61000 ferris 
RUN mkdir -p /usr/local/cargo/git; chown -R  ferris:ferris /usr/local/cargo
RUN mkdir -p /var/www; chown -R ferris:ferris /var/www
USER ferris

