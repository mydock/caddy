ARG CADDY_VERSION=2.6.2

FROM caddy:${CADDY_VERSION}-builder AS builder

RUN xcaddy build \
    --with github.com/caddy-dns/azure \
    --with github.com/caddy-dns/cloudflare \
    --with github.com/caddy-dns/googleclouddns \
    --with github.com/caddy-dns/route53 \
    --with github.com/caddyserver/replace-response \
    --with github.com/greenpau/caddy-security \
    --with github.com/abiosoft/caddy-json-parse \
    --with github.com/abiosoft/caddy-hmac \
    --with github.com/abiosoft/caddy-json-schema \
    --with github.com/chukmunnlee/caddy-openapi \
    --with github.com/chukmunnlee/abiosoft/caddy-named-routes \
    --with github.com/caddyserver/jsonc-adapter \
    --with github.com/hairyhenderson/caddy-teapot-module

FROM caddy:${CADDY_VERSION}

COPY --from=builder /usr/bin/caddy /usr/bin/caddy
