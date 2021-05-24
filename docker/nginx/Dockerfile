FROM nginx:1.20.0-alpine

RUN apk add ca-certificates

COPY . /var/www/html

COPY ./docker/nginx/default.conf /etc/nginx/conf.d/default.conf