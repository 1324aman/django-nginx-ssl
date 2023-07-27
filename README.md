# django-prod-setup

### For local setup, in .env.staging.proxy-companion file

set this variable `ACME_CA_URI=https://acme-staging-v02.api.letsencrypt.org/directory`.

### FOR PRODUCTION ONLY USE THIS

`ACME_CA_URI=https://acme-v02.api.letsencrypt.org/directory.`

Because this uri has rate limit. So if we run the containers again and again in local or staging then this uri might not work  after certain attempts.

#### For dev setup clone the repo and run `docker compose up --build`

#### For staging setup run `docker compose -f docker-compose.staging.yml up --build`

#### For prod setup run docker compose `docker compose -f docker-compose.prod.yml up --build`

Also I deployed this on aws. Steps are as follows -

1. I took the subdomain from here `https://www.duckdns.org/domains` and registered ec2 IP on this site. Also set the env variables `VIRTUAL_HOST` and `LETSENCRYPT_HOST` with your subdomain.
2. Create an ec2 instance and take clone of this repo.
3. To start the server run `docker compose -f docker-compose.prod.yml up --build `
