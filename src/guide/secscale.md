## Security
MoneroPay is meant to be run inside local network and **should not be exposed to the public internet**. If it needs to be exposed, we suggest reverse proxying using a web server. This way authentication and SSL encryption can be used to secure your connection.

Below is an example configuration for reverse proxying and enabling basic authentication on top of MoneroPay using Caddy2 web server.

`/etc/caddy/Caddyfile`:
```
moneropay.example.net {
	basicauth {
		admin your_password_hash
	}
	reverse_proxy localhost:5000
}
```
Generate the `your_password_hash` field using the `caddy hash-password` command.

## Scalability
It is possible differentiate MoneroPay instances based on their `X-Moneropay-Address` HTTP header. This header contains the wallet's primary address.
