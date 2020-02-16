FROM registry.gitlab.com/jamelleg/dockerfiles/rust:1.41.0-stable as builder
RUN rustup target add x86_64-unknown-linux-musl
RUN cargo install --target x86_64-unknown-linux-musl cargo-watch
FROM scratch
COPY --from=builder /usr/local/cargo/bin/cargo-watch .
ENTRYPOINT ["./cargo-watch"]
