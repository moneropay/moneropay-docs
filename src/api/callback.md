# Callback payload
MoneroPay contains a goroutine which checks for all incoming transactions every 30s and sends a `POST` request to `"callback_url"` specified in the [`POST /receive`](/api/receive.html#post-receive) endpoint with the folowing payload:
```json
{
  "amount": {
    "expected": 0,
    "covered": {
      "total": 200000000,
      "unlocked": 200000000
    }
  },
  "complete": true,
  "description": "Donation to Kernal",
  "created_at": "2022-07-11T19:04:24.574583Z",
  "transaction": {
    "amount": 200000000,
    "confirmations": 4799,
    "double_spend_seen": false,
    "fee": 9200000,
    "height": 2402648,
    "timestamp": "2022-07-11T19:19:05Z",
    "tx_hash": "0c9a7b40b15596fa9a06ba32463a19d781c075120bb59ab5e4ed2a97ab3b7f33",
    "unlock_time": 0
  }
}
```
> Additionally the same data can be retrieved via [`GET /receive/:address`](/api/receive.html#get-receiveaddress) endpoint and is encouraged to check regularly
> at the higher end application in case of a downtime, failed callback delivery or locked balances.
