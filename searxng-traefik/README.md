# Searxng + Traefik
[![Static Badge](https://img.shields.io/badge/mozilla_observatory-A%2B-green?style=flat&logo=mozilla)][1]

A docker-compose template for the [SearXNG] metasearch engine, using Traefik as a reverse proxy instead of the [default Caddy configuration][2]

Instead of keeping all the Traefik-related settings inside docker compose labels, i keep them in a separate file.

## Resources
- Other reverse proxy configuration examples: [searxng/searxng-docker issues][3].
- More details regarding Traefik configuration: [Traefik v2 instead of Caddy][4] issue.
- Nescessary `traefik.yml` settings: [My comment on "Traefik v2 instead of Caddy"][5] issue.

[1]: https://observatory.mozilla.org/analyze/searx.yonei.dev
[2]: https://github.com/searxng/searxng-docker/blob/master/Caddyfile
[3]: https://github.com/searxng/searxng-docker/issues
[4]: https://github.com/searxng/searxng-docker/issues/23
[5]: https://github.com/searxng/searxng-docker/issues/23#issuecomment-1442049821

[SearXNG]: https://github.com/searxng/searxng
