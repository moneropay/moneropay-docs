# Options

The configuration parameters for MoneroPay are as follows:

```
$ ./moneropay -h
Usage of ./moneropay:
  -bind="localhost:5000": Bind address:port for moneropayd
  -config="": Path to configuration file
  -log-format="pretty": Log format (pretty or json)
  -poll-frequency=5s: Interval for checking new incoming and pool payments.
  -postgresql="postgresql://moneropay:s3cret@localhost:5432/moneropay": PostgreSQL connection string
  -rpc-address="http://localhost:18082/json_rpc": Wallet RPC server address
  -rpc-password="": Password for monero-wallet-rpc
  -rpc-username="": Username for monero-wallet-rpc
  -sqlite="": SQLite3 connection string
  -transfer-mixin=8: Number of outputs from the blockchain to mix with (0 means no mixing)
  -transfer-priority=0: Set a priority for transactions
  -transfer-unlock-time=10: Number of blocks before the monero can be spent (0 to not add a lock)
  -zero-conf=false: Enable 0-conf mode. Sends 3 callbacks (0-conf, 1-conf, 10-conf).
```

These parameters are also available as environment variables. For example, `--log-format` can be configured by setting `LOG_FORMAT`.