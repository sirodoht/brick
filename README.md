# brick

Server configuration files for brick.01z.io

## Commands

```sh
uv run ansible-playbook -v playbook.yaml
```

## Deployment

Pushes to `main` run the Ansible playbook through GitHub Actions. Install each
application's Caddy snippet on Brick before adding its import to `Caddyfile.j2`.
The template is validated with Caddy before replacing the live configuration,
and the previous file is backed up. Invalid configuration leaves the live file
and running service unchanged. Valid changes reload Caddy through a handler;
unchanged deployments do not restart it.

## License

Copyright sirodoht

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU Affero General Public License as published by the Free
Software Foundation, version 3.
