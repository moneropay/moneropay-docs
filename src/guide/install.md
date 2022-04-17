# Installation

## Docker Compose
The MoneroPay repository contains docker-compose.yaml which is a complete setup of MoneroPay + PostgreSQL + monero-wallet-rpc.

Create an `.env` file from the `.env.example` and configure it.
```sh
cp .env.example .env
vim .env
```
Bring it up.
```sh
docker compose up -d
```

## Native
Running MoneroPay without Docker.

### Prerequisites
* Go compiler
* PostgreSQL server (and an empty database)
* monero-wallet-rpc server

### Compilation
```sh
go install gitlab.com/moneropay/moneropay/v2@latest
`go env GOPATH`/bin/moneropay -h
```
Now MoneroPay is installed in your `${GOPATH}/bin`.
