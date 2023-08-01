Bitcoin Cash Orb (Proof-of-Concept)
================

Disclaimer
----------
This is the first time I've touched JavaScript since the 90s. Most of it is written whilst intoxicated on alcohol and I don't intend to actually launch this project in a good state.

Usage
-----
Save the html file on your computer and open it in your browser. You can use the [Cashonize wallet](https://cashonize.com/) to generate a seed and receive chipnet coins in a [faucet](https://tbch.googol.cash/#info).

What is this?
-------------
This is a re-implementation of the Ethereum contract [Erics Orb](https://eric.orb.land/) but for Bitcoin Cash and demonstrates that it is possible to use a [Harberger Tax](https://en.wikipedia.org/wiki/Harberger_Tax) on UTXOs.
There are some slight modifications, most notably a buyer of the orb gets 25% of the taxes payed by the previous holder to incentivize a high locktime on the transaction to buy the orb.

The Orb cooldown has also been reduced to 24 hours (144 blocks) to have more fun here on a testnet!

Roadmap
-------
I will probably not do anything with the code here and will most certainly not deploy it on mainnet.

However, there are some major glaring things to be fixed for anyone that want to fork it:
* Store transactions in the browser. Currently all transactions are fetched and parsed **every time you refresh the page**. This opens up the whole thing for
some serious DoS attacks (spam the oracles p2pkh and see the whole thing just kind of die...).
* Fee estimation. I kind of just gave up and slapped on a couple of hundreds of sats on each input/output.
* Input consolidation. Related to above: I just consolidate all inputs each time, so if anyone spams a couple of hundred inputs with dust to a user the webapp is kind of unusable.
* Everything UX. 'nuff said.
* Refactoring the code so it makes sense. I just wrote stuff as I came up with new ideas and kind of just let it stay like that.

Acknowledgements
----------------
This app is built with [mainnet.cash](https://mainnet.cash). \
I have also googled and copied JavaScript snippets from all over and hopefully commented in the code where applicable.