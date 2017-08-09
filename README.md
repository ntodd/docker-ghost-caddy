# Description

docker-ghost-caddy will set up a [Ghost blog](https://ghost.org/) behind a Caddy proxy on Docker Compose. Your blog will be secured by an SSL certificate from Let's Encrypt.

# Setup

1. Clone repository to your server
2. `cp proxy/Caddyfile-example proxy/Caddyfile`
3. In `proxy/Caddyfile` change `your.domain.here` and `you@email.com` to your blog's domain and your email (email used for generation of SSL certificate)
4. In `docker-compose.yml` change `https://your.domain.here` to your https domain
5. Ensure your DNS record is pointed at your server. If it is not, Let's Encrypt will not be able to generate your SSL cert and Caddy will fail to start.
6. Run `docker-compose build` to build the docker images

# Operation

Run `docker-compose up -d` to run in detached mode

Run `docker-compose stop` to stop

# Notes

The Ghost service mounts the `ghost/content` directory where you can access all your blog data.
