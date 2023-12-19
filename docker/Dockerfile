#syntax=docker/dockerfile:1.4

# pin versions
FROM ghcr.io/shopware/docker-base:8.2 as base-image
FROM ghcr.io/friendsofshopware/shopware-cli:0.4.2-php-8.2 as shopware-cli

# build

FROM shopware-cli as build

COPY --link . /src
WORKDIR /src

RUN --mount=type=secret,id=composer_auth,dst=/src/auth.json \
    --mount=type=cache,target=/root/.composer \
    --mount=type=cache,target=/root/.npm \
    /usr/local/bin/entrypoint.sh shopware-cli project ci /src

# build final image

FROM base-image

COPY --from=build --chown=www-data /src /var/www/html
