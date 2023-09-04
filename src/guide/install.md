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

Create the data directory and add your wallet files.
```sh
mkdir -p data/wallet
cp wallet{,.keys} data/wallet
touch data/wallet/wallet.passwd # if your wallet is password protected, write it in this file. Else leave empty.
chown -R 1000:1000 data/wallet # change owner to prevent permission errors
```
> Docker compose configuration expects the wallet keys file to be called `wallet.keys`. You can choose to rename your wallet keys file or change the name in the `docker-compose.yaml` file.

Now you should have 3 files under `data/wallet` directory: `wallet`, `wallet.keys` and `wallet.passwd`.

Bring it up.
```sh
docker compose up -d
```

You can check the logs using:
```sh
docker compose logs -f
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
go build
```
Now MoneroPay help page can be checked via `./moneropay -h`
