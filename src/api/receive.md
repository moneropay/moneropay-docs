## POST /receive
Create a subaddress for incoming transfers.
### Request
```sh
curl -s -X POST "${endpoint}/receive" \
  -H 'Content-Type: application/json' \
  -d '{"amount": 123000000, "description": "Server expenses", "callback_url": "http://merchant/callback/moneropay_tio2foogaaLo9olaew4o"}'
```
> `"complete"` will be set to `true` inside callback and `GET /receive/:subaddress` payload,
> when unlocked amount is equal or more to the one specified in `"amount"`.

> `"description"` and `"callback_url"` are optional.
> If `"callback_url"` is set, MoneroPay will send a POST request to URL specified with a payload described [here](/api/callback.html).
### Response
```json
{
  "address": "84WsptnLmjTYQjm52SMkhQWsepprkcchNguxdyLkURTSW1WLo3tShTnCRvepijbc2X8GAKPGxJK9hfQhLHzoKSxh7y8Yqrg",
  "amount": 123000000,
  "description": "Server expenses",
  "created_at": "2022-07-18T11:54:49.780542861Z"
}
```
## GET /receive/:address 
View incoming transfers for a subaddress.
### Request
```sh
curl -s -X GET "${endpoint}/receive/${address}?min=${min_height}&max=${max_height}"
```
> Optionally filter `"transactions"` by `min` and `max` block height.
### Response
```json
{
  "amount": {
    "expected": 200000000,
    "covered": {
      "total": 200000000,
      "unlocked": 200000000
    }
  },
  "complete": true,
  "description": "Donation to Kernal",
  "created_at": "2022-07-11T19:04:24.574583Z",
  "transactions": [
    {
      "amount": 200000000,
      "confirmations": 10,
      "double_spend_seen": false,
      "fee": 9200000,
      "height": 2402648,
      "timestamp": "2022-07-11T19:19:05Z",
      "tx_hash": "0c9a7b40b15596fa9a06ba32463a19d781c075120bb59ab5e4ed2a97ab3b7f33",
      "unlock_time": 0,
      "locked": false
    }
  ]
}
```
