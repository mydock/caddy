ARG CADDY_VERSION=2.6.2

FROM caddy:${CADDY_VERSION}-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/azure \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/caddy-dns/googleclouddns \
    --with github.com/caddy-dns/route53 \
    --with github.com/caddyserver/replace-response \
    --with github.com/greenpau/caddy-security \
    --with github.com/hairyhenderson/caddy-teapot-module@v0.0.3-0

FROM caddy:${CADDY_VERSION}

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
