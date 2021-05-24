# FROM composer:2.0.13 as vendor

#COPY composer.json composer.json
#COPY composer.lock composer.lock

# RUN composer install \
#     --ignore-platform-reqs \
#     --no-interaction \
#     --no-plugins \
#     --no-scripts \
#     --prefer-dist

# FROM node:14 as frontend

#RUN mkdir -p /app/public

#COPY package.json webpack.mix.js package.lock /app/
#COPY resources/assets/ /app/resources/assets/

# WORKDIR /app

# RUN npm install && npm production

FROM php:8.0.6-fpm-alpine

COPY . /var/www/html
#COPY --from=vendor /app/vendor/ /var/www/html/vendor/
#COPY --from=frontend /app/public/js/ /var/www/html/public/js/
#COPY --from=frontend /app/public/css/ /var/www/html/public/css/
#COPY --from=frontend /app/mix-manifest.json /var/www/html/mix-manifest.json

COPY ./docker/php-fpm/custom.ini $PHP_INI_DIR/conf.d/

CMD ["php-fpm"]
