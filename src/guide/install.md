# Installation

## Docker Compose
The MoneroPay repository contains docker-compose.yaml which is a complete setup of MoneroPay + PostgreSQL + monero-wallet-rpc.

Create the `.env`, `docker-compose.override.yaml` files from the `.env.example`, `docker-compose.override.yaml.example` and configure it.
```sh
cp .env.example .env
cp docker-compose.override.yaml.example docker-compose.override.yaml
vim .env
vim docker-compose.override.yaml
```

Start MoneroPay and its dependencies. If no wallet file was provided, MoneroPay will create a new wallet under `./data/wallet`. The wallet auto-creation feature was introduced in version 2.7.0.
```sh
docker compose up -d
```

## Native
Running MoneroPay without Docker.

### Prerequisites
* Go compiler
* PostgreSQL server (and an empty database)
* monero-wallet-rpc server
* A Monero wallet (view-only or full)

### Compilation
```sh
git clone https://gitlab.com/moneropay/moneropay.git
cd moneropay
go build ./cmd/moneropay
```
Now MoneroPay help page can be checked via `./moneropay -h`
