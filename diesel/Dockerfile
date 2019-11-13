#TODO: setup rust development environment
FROM rust:1.39.0 as builder

RUN apt-get update

RUN apt-get install musl-tools -y

RUN rustup target add x86_64-unknown-linux-musl

RUN RUSTFLAGS=-Clinker=musl-gcc cargo install --target x86_64-unknown-linux-musl diesel_cli --no-default-features --features postgres

FROM alpine:latest 

COPY --from=builder /usr/local/cargo/bin/diesel /bin/

RUN apk add --no-cache ca-certificates

RUN apk add libpq

WORKDIR /var/www




