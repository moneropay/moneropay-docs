## POST /transfer
Transfer to a single or multiple recipients. If necessary, split the transfer into multiple transactions.
### Request
```sh
curl -s -X POST "${endpoint}/transfer" \
	-H 'Content-Type: application/json' \
	-d '{"destinations": [{"amount": 1337000000, "address": "47stn..."}]}'
```
> This transaction uses balance of the wallet's Primary Account.
### Response
```json
{
  "amount": 1337000000,
  "fee": 87438594,
  "tx_hash": "5ca34...",
  "tx_hash_list": ["5ca34...", "cf448..."],
  "destinations": [
    {
      "amount": 1337000000,
      "address": "47stn..."
    }
  ]
}
```

## GET /transfer/:tx_hash
Get information about transaction via its hash.
### Request
```sh
curl -s -X GET "${endpoint}/transfer/${tx_hash}"
```
### Response
```json
{
  "amount": 79990000,
  "fee": 9110000,
  "state": "completed",
  "transfer": [
    {
      "amount": 79990000,
      "address": "453biCQpM6oSSr7jgTwmtC9YfiXUWZY1wEfSZJD4r6rf7mPqPj8NZpp7WYpAHVq7p69SYa1B1zMN6SeRc8exYi1WEenqu2c"
    }
  ],
  "confirmations": 15,
  "double_spend_seen": false,
  "height": 2407445,
  "timestamp": "2022-07-18T11:37:50Z",
  "unlock_time": 10,
  "tx_hash": "cf448effb86f24f81476c0012a6636700488e13accd91f8f43302ae90fed25ce"
}
```
