FROM caddy:2.7.6-builder-alpine AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/acouvreur/sablier/plugins/caddy \
    --with github.com/hslatman/caddy-crowdsec-bouncer/http

FROM caddy:2.7.6-alpine

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
