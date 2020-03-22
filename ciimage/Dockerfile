FROM adoptopenjdk/openjdk11:jdk-11.0.5_10-alpine as builder
RUN apk update && \
    apk add bash curl su-exec tzdata libpq postgresql-client postgresql postgresql-contrib && \
    rm -rf /var/cache/apk/*

ENV POSTGRES_USER postgres
ENV POSTGRES_DB postgres
ENV POSTGRES_PASSWORD postgres
ENV PGDATA /var/lib/postgresql/data

USER postgres
RUN initdb -A trust -D /var/lib/postgresql/data
COPY ./postgres/postgresql.conf /var/lib/postgresql/data/postgresql.conf
