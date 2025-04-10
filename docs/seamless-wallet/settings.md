---
sidebar_position: 1
---

# Settings

In Seamless Wallet integrations, our system does not store players’ money, so in each case when it is required to withdraw money from a player’s account, a callback-request to your system is going to be made.

To set up Seamless Wallet, you need provide the following information to us:

- CALLBACK_URL. This is the URL for request to get a balance and money deposit/withdrawal.
- SECRET_KEY. This is the Key that is used to sign requests.