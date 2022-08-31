## Security
MoneroPay is meant to be run inside local network and **should not be exposed to the public internet**. If it needs to be exposed, we suggest reverse proxying using a web server. This way authentication and SSL encryption can be used to secure your connection.

## Scalability
It is possible differentiate MoneroPay instances based on their `X-Moneropay-Address` HTTP header. This header contains the wallet's primary address.
