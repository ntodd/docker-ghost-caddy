# Usage

1. Clone repository to your server
2. `cp proxy/Caddyfile-example proxy/Caddyfile`
3. In `proxy/Caddyfile` change `your.domain.here` and `you@email.com` to your blog's domain and your email
4. Run `docker-compose up -d`

Ghost will mount the `ghost/` directory where you can access all your data.

NOTE: The DNS for your domain must be configured for Let Encrypt to generate your SSL certificate.  Caddy will fail to launch if your server is inaccessible.
