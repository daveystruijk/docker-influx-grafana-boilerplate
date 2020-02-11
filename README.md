# Docker + InfluxDB + Grafana + Nginx

This repo contains a docker-compose setup with:
- InfluxDB
- Grafana
- Nginx

## Development

To start using it, simply clone the repo and execute `./run.sh`.

Then in Grafana, you can add `http://influx:8086` as a Data Source to connect to it.

## Production

The `docker-compose.prod.yml` also contains some additional config for production environments:
- HTTPS (w/ Letsencrypt)

First, you should setup [https://certbot.eff.org/](Certbot) on the host to automatically manage certificates for your domain. Then, edit `nginx/conf.d.prod/grafana.conf` and change `my.example.com` to the correct domain.

After doing the above, you can execute `./run_prod.sh` to (re)start the server.
