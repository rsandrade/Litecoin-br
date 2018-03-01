# Xadrez 
**Open Source solution for e-commerce store that accepts BTC and LTC**

## Introduction

TThis tutorial expect to give directions to anyone who want to setup an ecommerce store that accepts Bitcoin (BTC) and Litecoin (LTC). Old payment methods like credit card and stuff can be enabled too. All components of the solution are open source software and can be obtained at their project websites.

The ecoomerce store we want to setup need to use stable software, easy to configure by merchants with no more than basic tech skills and be able to show products, handle carts, inventory, customer accounts, generate reports and others expected characteristcs. The crypto funds received need to go directly to the merchant's (preferable mobile) wallets.

## Infrastructure



## Components

>> [Wordpress](https://www.wordpress.org)

*"WordPress started in 2003 with a single bit of code to enhance the typography of everyday writing and with fewer users than you can count on your fingers and toes. Since then it has grown to be the largest self-hosted blogging tool in the world, used on millions of sites and seen by tens of millions of people every day."*

Wordpress is the foundation of the store. On it, we will install a plugin to convert this content management system into a full featured ecommerce store.

>> [WooCommerce](https://woocommerce.com)

*WooCommerce is an open-source, completely customizable eCommerce platform for entrepreneurs worldwide. Go beyond the confines of traditional eCommerce solutions, and be limited only by your own imagination.*

This is the plugin I mentioned above. WooCommerce is widely used and offer a bunch of good quality addons to improve your store.

>> [BTCpay](https://github.com/btcpayserver/btcpayserver)

*BTCPay Server is a free and open source server for merchants wanting to accept Bitcoin for their business. The API is compatible with Bitpay service to allow seamless migration.*

BTCpay Server will will turn the merchant into a self sovereign one. The merchant (or some merchants who trust themselves) will run a payment gateway and link the store (Wordpress + WooCommerce) to it using a Woocommerce addon plugin from BTCpayServer project. 

The recommended infrastructure to setup this environment can be purchased at [Digital Ocean](https://m.do.co/c/ec2caf98348a). You can create your Droplet for BTCpay Server (check about BTCpay below) using an *One-click apps* image called *Docker 17.12.0~ce on 16.04*, the plan *2 GB, 1 vCPU, 50 GB, 2 TB* will costs $10/mo.

You will need to prune the ```bitcoind``` including a new line with argument ```prune=2000M``` at BITCOIN_EXTRA_ARGS in ```docker-compose.btc-ltc.yml``` file. Do not prune ```litecoind```.

>> [Samourai Wallet](https://samouraiwallet.com/)

*A modern bitcoin wallet hand forged to keep your transactions private, your identity masked, and your funds secure.*

>> [Loafwallet](https://www.loadwallet.org)
