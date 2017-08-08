# Usage

1. Clone repository to your server
2. `cp proxy/Caddyfile-example proxy/Caddyfile`
3. In `proxy/Caddyfile` change `your.domain.here` and `you@email.com` to your blog's domain and your email
4. Run `docker-compose up -d`

Ghost will mount the `ghost/` directory where you can access all your data.
