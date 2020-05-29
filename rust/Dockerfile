FROM rust:{RUST_VERSION}{DOCKER_TYPE}

RUN groupadd --gid 1001 ferris \
    && useradd --uid 1001 --gid ferris --no-log-init --shell /bin/bash --create-home ferris

RUN rustup component add rustfmt

RUN cargo install watchexec \
 && rm -rf $CARGO_HOME/registry \
 && rm -rf $CARGO_HOME/git

RUN apt-get update && \
	apt-get install -y libssl-dev pkg-config && \
    rm -rf /var/lib/apt/lists/*

RUN mkdir -p /usr/ferris/target && chown ferris:ferris /usr/ferris/target
 
WORKDIR /usr/ferris
EXPOSE 3001
USER ferris
