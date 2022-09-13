# Table of Endpoints
| Method | URI                            | Input                                                                                 |
| :----: | ------------------------------ | ------------------------------------------------------------------------------------- |
| `GET`  | /balance                       |                                                                                       |
| `GET`  | /health                        |                                                                                       |
| `POST` | /receive                       | `{"amount": 123000000, "description": "Stickers", "callback_url": "http://merchant"}` |
| `GET`  | /receive/:address?min=&max=    |                                                                                       |
| `POST` | /transfer                      | `{"destinations": [{"amount": 1337000000, "address": "47stn..."}]}`                   |
| `GET`  | /transfer/:tx_hash             |                                                                                       |

> All the amount fields are in atomic units, also known as [piconero](https://www.getmonero.org/resources/moneropedia/denominations.html).
