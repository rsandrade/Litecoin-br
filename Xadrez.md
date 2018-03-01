<img src="./img/xadrez.jpg" width="16%"><br>
# Xadrez 
**Seeking the best open source setup for an e-commerce store that accepts Litecoin (LTC) and Bitcoin (BTC)**

*This guide is not finished yet (I expect to put images and describe everything step-by-step). At this stage you can get good ideas and directions to build your own e-store. If you consider this useful, contribute with some lites to LTC address: [LdMwrnsBoggWVcHcM7yeg242e8QqetYAzU](https://live.blockcypher.com/ltc/address/LdMwrnsBoggWVcHcM7yeg242e8QqetYAzU/)*

## Introduction

This tutorial expect to give directions and tools to anyone who want to setup an ecommerce store that accepts Litecoin (LTC) and Bitcoin (BTC). Old payment methods like credit card and stuff can be enabled too. All components of the solution are open source software and can be obtained at their project websites.

This setup is called Xadrez just to turn easier to anyone who want to refer the proposal presented here. Xadrez is Chess in portuguese language and we will change the pieces (the components) on the board until we reach a very nice full featured setup, stable and definitive ecommerce store (the Checkmate). 

The ecommerce store we want to setup will need to use stable software, easy to configure by merchants with no more than basic tech skills and be able to show products, handle carts, inventory, customer accounts, generate reports and others expected capabilities. The crypto funds received need to go directly to the merchant's (preferable mobile) wallets.

## Components

Actual setup of Xadrez is compose of the components listed and described below.

> [Wordpress](https://www.wordpress.org)

*"WordPress started in 2003 with a single bit of code to enhance the typography of everyday writing and with fewer users than you can count on your fingers and toes. Since then it has grown to be the largest self-hosted blogging tool in the world, used on millions of sites and seen by tens of millions of people every day."*

Wordpress is a popular Content Management System (CMS) used to run portals, websites, blogs and many different kinds of websites. We will use it to run the store. A plugin (Woocommerce) will convert this content management system into a full featured ecommerce store as described below.

The minimum infrastructure to setup this can be purchased at [Digital Ocean](https://m.do.co/c/ec2caf98348a). You can create your Droplet for Wordpress using an *One-click apps* image called *Wordpress 4.9.1 on 16.04* or higher on the plan described as *1 GB, 1 vCPU, 25 GB, 1 TB* will costs $5/mo.

> [WooCommerce plugin](https://woocommerce.com)

*WooCommerce is an open-source, completely customizable eCommerce platform for entrepreneurs worldwide. Go beyond the confines of traditional eCommerce solutions, and be limited only by your own imagination.*

This is the plugin mentioned above. WooCommerce is widely used and offer a bunch of good quality addons to improve your store.

> [BTCpay](https://github.com/btcpayserver/btcpayserver)

*BTCPay Server is a free and open source server for merchants wanting to accept Bitcoin for their business. The API is compatible with Bitpay service to allow seamless migration.*

BTCpay Server will will turn the merchant into a self sovereign one. The merchant (or some merchants who trust themselves) will run a payment gateway and link the store (Wordpress + WooCommerce) to it using a Woocommerce addon plugin from BTCpayServer project. 

The minimum infrastructure to setup this can be purchased at [Digital Ocean](https://m.do.co/c/ec2caf98348a). You can create your Droplet for BTCpay Server (check about BTCpay below) using an *One-click apps* image called *Docker 17.12.0~ce on 16.04* on the plan described as *2 GB, 1 vCPU, 50 GB, 2 TB* will costs $10/mo.

You will need to prune the ```bitcoind``` including a new line with argument ```prune=2000M``` at BITCOIN_EXTRA_ARGS in ```docker-compose.btc-ltc.yml``` file. Do not prune ```litecoind```.

> ["Wordpress-Woocommerce-BTCpay" plugin](https://github.com/btcpayserver/woocommerce-plugin)

*Add the ability to accept Bitcoin and Litecoin in WooCommerce via BTCpay Server.*

This plugin will link BTCpay Server and Wordpress+WooCommerce.

> [Samourai Wallet](https://samouraiwallet.com/)

*A modern bitcoin wallet hand forged to keep your transactions private, your identity masked, and your funds secure.*

Samourai will provide us the Derivation Scheme necessary to inform BTCpay Server. Derivation Scheme will generate different addresses (public keys) to every order at store.

To get the Derivation Scheme - at Samourai Wallet - you need to click upper right icon, choose Settings, Choose Wallets and decide if you want or not to use segwit addresses. Segwit is extremely recommended. Use the Segwit YPUB code at BTCpay Server to generate Segwit addresses which will send the funds to your Samourai wallet.

TODO: Nicolas Dorier, BTCpay Server maintener, [was in doubt about the gap limit of Samourai](https://twitter.com/NicolasDorier/status/968638958438572032). Need to be checked to validate the use of Samourai Wallet.

> [Electrum-LTC](https://electrum-ltc.org/)

*Electrum-LTC is a simple, but powerful Litecoin wallet. A twelve-word security passphrase (or “seed”) leaves intruders stranded and your peace of mind intact.*

Electurm-LTC is not a mobile wallet but will generate the Derivation Scheme you need to fill the field at BTCpay Server.

The Electrum-LTC website inform the gap limit as 5 by default and appear it needs to be changed to 20 due [the requirement of BTCpay Server](https://twitter.com/NicolasDorier/status/968638958438572032).

The segwit addresses will be generated using bech32 format, not compatible with some wallets yet and it can be a problem for customers until wallets upgrade to that format.

> [Loafwallet](https://www.loadwallet.org)

*Loafwallet is the best standalone Litecoin wallet built for iOS and Android. It is available to download for free on the Apple App Store and Play Store!*

Loafwallet will be the best choice for accept LTC in Xadrez setup when archive some requirements as listed:
  - Be compatible with segwit (probably at 2.1 version)
  - Inform the Derivation Scheme
  - Has the recommended gap limit of 20 addresses
