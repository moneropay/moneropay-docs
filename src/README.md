# Introduction
Welcome to the MoneroPay documentation. Here you will find information on how to deploy it and API specification.

![MoneroPay banner - Logo by @mondetta, mascot by @siren](/images/mpay-banner.webp)
_MoneroPay logo by Mondetta, mascot by Siren._

- Project main repository: [https://gitlab.com/moneropay/moneropay](https://gitlab.com/moneropay/moneropay)
- Matrix: [https://matrix.to/#/#moneropay:kernal.eu](https://matrix.to/#/#moneropay:kernal.eu)
- GitHub mirror: [https://github.com/moneropay/moneropay](https://github.com/moneropay/moneropay)
- Commercial support: Contact us at [info@digilol.net](mailto:info@digilol.net)

Feel free to open a [PR](https://gitlab.com/moneropay/moneropay/-/merge_requests), raise an [issue](https://gitlab.com/moneropay/moneropay/-/issues) or request a new feature.

For related discussions join our [Matrix room](https://matrix.to/#/#moneropay:kernal.eu).

## What is this?
A backend service for receiving, sending and tracking status of Monero payments.

MoneroPay provides a simple HTTP API for merchants or individuals who want to accept XMR.

MoneroPay supports optional status updates via HTTP Callbacks.

MoneroPay is not a plugin for an existing e-commerce solution.
It is a standalone backend daemon that can be used for any purpose.
Some use cases are:
- Online stores/e-commerce
- Donation/fundraiser websites
- ATMs
- Paid services like parking or bus ticket applications
- Shell scripts and programs for any purpose

MoneroPay utilizes:
 - Monero Wallet RPC
 - PostgreSQL (or SQLite)
