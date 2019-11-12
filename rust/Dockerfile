FROM rust:{RUST_VERSION}
RUN rustup toolchain uninstall stable
RUN rustup toolchain install {RUST_TOOLCHAIN} && rustup component add --toolchain {RUST_TOOLCHAIN} rustfmt
WORKDIR /var/www
EXPOSE 3001
RUN groupadd -g 61000 ferris 
RUN useradd -g 61000 -l -M -s /bin/false -u 61000 ferris 
USER ferris

RUN chown -R ferris:ferris /var/www

VOLUME ["/usr/local/cargo","/var/www/target"]
