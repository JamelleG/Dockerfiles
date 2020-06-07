#TODO: setup rust development environment
FROM rust:1.43.1-slim-buster as builder

RUN apt-get update

RUN apt-get install -y musl-tools libpq-dev libsqlite3-dev default-libmysqlclient-dev

RUN rustup target add x86_64-unknown-linux-musl

RUN RUSTFLAGS=-Clinker=musl-gcc cargo install --target x86_64-unknown-linux-musl diesel_cli 

FROM alpine:latest 

COPY --from=builder /usr/local/cargo/bin/diesel /bin/

RUN apk add --no-cache ca-certificates

RUN apk add libpq mysql-dev sqlite-dev && rm -rf /var/cache/apk/*
