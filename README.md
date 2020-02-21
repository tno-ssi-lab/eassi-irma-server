# SSI Service Provider IRMA server

This repo contains all configuration and files necessary to run the IRMA
validation server for the SSI Service Provider.

## Configuration

For configuring the IRMA server, see the
[IRMA docs](https://irma.app/docs/irma-server/#configuring).

Settings can be changed by modifying the `irmaserver.json` file or by
setting `IRMASERVER_<SETTING_NAME>` environment variable, for instance
through `docker-compose.yml`.

## Generating a key-pair for RS256

You can generate a key-pair for use in the jwt RS256 algorithm with the
following commands:

```bash
ssh-keygen -t rsa -b 4096 -m PEM -f jwtRS256.key
openssl rsa -in jwtRS256.key -pubout -outform PEM -out jwtRS256.key.pub
```
