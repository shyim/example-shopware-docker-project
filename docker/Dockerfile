#syntax=docker/dockerfile:1.4

# pin versions
FROM shopware/docker-base:8.3 as base-image

COPY --chown=www-data --link . /var/www/html
