FROM alpine:latest

WORKDIR /app

COPY . /app

RUN apk add openssl
RUN apk add python3
RUN apk add ansible
# First failure is need to install ssh
