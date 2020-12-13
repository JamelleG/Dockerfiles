#TODO: setup rust development environment
FROM ekidd/rust-musl-builder:latest as builder

RUN cargo install sqlx-cli 

FROM alpine:latest 

COPY --from=builder /home/rust/.cargo/bin/sqlx /bin/

RUN apk add --no-cache ca-certificates

RUN apk add libpq mysql-dev sqlite-dev && rm -rf /var/cache/apk/*
