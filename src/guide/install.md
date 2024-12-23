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

### Using an Existing Wallet
You can follow these steps to use a wallet that you generated on your own. You might want to do this to use a view-only wallet or set a wallet password.

> Using a "dirty" wallet (a wallet with existing subaddresses) will result in untracked subaddresses and may result in database errors due to it not being in sync with MoneroPay.

Create the data directory and add your wallet files.
```sh
mkdir -p data/wallet
cp wallet{,.keys} data/wallet
touch data/wallet/wallet.passwd # if your wallet is password protected, write it in this file. Else leave empty.
chown -R 1000:1000 data/wallet # change owner to prevent permission errors
```
> Docker compose configuration expects the wallet keys file to be called `wallet.keys`. You can choose to rename your wallet keys file or change the name in the `docker-compose.yaml` file.

Now you should have 3 files under `data/wallet` directory: `wallet`, `wallet.keys` and `wallet.passwd`.

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
