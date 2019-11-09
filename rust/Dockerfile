FROM rust:{RUST_VERSION}
RUN rustup toolchain uninstall stable
RUN rustup toolchain install {RUST_TOOLCHAIN} && rustup component add --toolchain {RUST_TOOLCHAIN} rustfmt
WORKDIR /var/www
EXPOSE 3001
RUN adduser -D ferris 
USER ferris

RUN chown -R ferris:ferris /var/www

VOLUME ["/usr/local/cargo","/var/www/target"]
