# Introduction
Welcome to the MoneroPay documentation. Here you will find information on how to deploy it and API specification.
```
    .-"""-.
   /       \
  |__/\_/\__|
   \       /
    '-...-' 
       _
    \('v')/
     /   \
    (\_ _/)
     ^^ ^^
```

Feel free to open a [PR](https://gitlab.com/moneropay/moneropay/-/merge_requests), raise an [issue](https://gitlab.com/moneropay/moneropay/-/issues) or request a new feature.

For related discussions join our [Matrix room](https://matrix.to/#/#moneropay:kernal.eu).

We also offer commercial support for merchants and developers. Contact us at [info@digilol.net](mailto:info@digilol.net).

## What is this?

MoneroPay is a simple backend service for merchants, developers and everyone who is looking to accept XMR. It sits on top of a wallet RPC server instance and provides a simple API. When you’re expecting a payment, MoneroPay can notify you with callbacks whenever the payment is partially or fully completed.

MoneroPay is not a plugin for an existing e-commerce solution. It’s a standalone backend daemon. For this reason, it can be used for anything. Some use cases are:
- Online stores/e-commerce.
- In-game purchases.
- Donation/fundraiser websites.
- Paid services like parking or bus ticket applications.
- Shell scripts and programs for any purpose.
