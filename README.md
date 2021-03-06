# SELFMiner
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=A8YE92K9QM7NA)

Mining Litecoin(Open Source) on Ubuntu OS by using CPUMiner(Open Source) connect to litecoinpool.org (For miners who want to mine Litecoin by yourself).

note : all fee-free!!!

[![ScreenShot](https://i.ytimg.com/vi/Um63OQz3bjo/hqdefault.jpg)](https://youtu.be/Gc2en3nHxA4)

## Requirement

- [x] Server
- [x] Wallet 
- [x] Miner
- [x] Pool

## Wallet

Without a Bitcoin wallet, you can’t send or receive Bitcoin payments. So before you get bitcoins, you’ll need to buy, download, or create a bitcoin wallet. There are different types of wallets: [more detail here](https://www.weusecoins.com/en/find-the-best-bitcoin-wallet/)

##### Installation

I recommended `Litecoin` wallet. Install it into your server :

```
wget https://github.com/downloads/litecoin-project/litecoin/litecoin-0.6.3c-linux.tar.gz
tar xzvf litecoin-0.6.3c-linux.tar.gz
cd litecoin-0.6.3c-linux/bin/##
sudo apt-get install libqtgui4
```

some one need this option :

```
sudo apt-get install libqtgui4:amd64
```

note : `##` in `cd litecoin-0.6.3c-linux/bin/##` means 32 or 64, it's base on your OS

##### Config your wallet

To use litecoind, you must set a rpcpassword in the configuration file `/home/ubuntu/.litecoin/litecoin.conf`. It is recommended you use the following random password :

```
rpcuser=ANY_USERNAME
rpcpassword=ANY_PASSWORD
```

Create litecoin.conf :

```
sudo nano /home/ubuntu/.litecoin/litecoin.conf
```

And modify it look like this :

```
rpcuser=ANY_USERNAME
rpcpassword=ANY_PASSWORD
rpcallowip=127.0.0.1
rpcport=9332
daemon=1
server=1
gen=0
```

##### Start Litecoin wallet service

```
cd ~/litecoin-0.6.3c-linux/bin/##
./litecoind
```

##### Stop the service

```
./litecoind stop
```

##### Create new wallet address

```
./litecoind getnewaddress YOUR_RPC_USER
```

note : Litecoin will return wallet address to you, it used to regist in litecoinpool.org

## litecoinpool.org

You need to register to the [pool](www.litecoinpool.org) first.
Set your Litecoin wallet address in `My Account` page.
After setting your account. It will show mining command look like this :

```
./minerd --algo=scrypt --url=stratum+tcp://HOST:PORT --userpass=WORKERNAME:PASSWORD
```

The command used to connect between `cpuminer` and `litecoin.org`.
Or you can download `mine.sh` from the website.

## Stratum protocal

Stratum is a proposal for an open source client-server `overlay` protocol that enables thin clients. It is currently used by Electrum. While originally announced right before 2012, the protocol has not yet been completed and proposed as a BIP for standardisation.

##### Installation

```
sudo apt-get install python-dev
git clone https://github.com/slush0/stratum-mining-proxy
cd stratum-mining-proxy
sudo python setup.py install
```

## CPUMiner

It is a multi-threaded, highly optimized CPU miner for Litecoin, Bitcoin, and other cryptocurrencies. Currently supported algorithms are SHA-256d and scrypt(N, 1, 1). It supports the getblocktemplate mining protocol as well as the Stratum mining protocol, and can be used for both solo and pooled mining.

ref : https://github.com/pooler/cpuminer

##### Installation

```
sudo apt-get install build-essential autoconf automake libtool pkg-config libcurl3-dev libudev-dev
git clone https://github.com/pooler/cpuminer
cd cpuminer
sh autogen.sh
./configure CFLAGS="-O3"
make
```

Now, you can mine Litecoin by using `./minerd --algo=scrypt --url=stratum+tcp://HOST:PORT --userpass=WORKERNAME:PASSWORD`.

Enjoy!!!

## Option

Mining Litecoin by using CPU, it will take many many many cost from your resources. For miner who don't care about it. I found some tools to support you :

##### CPULimit

Set your limit of CPU usage : `https://github.com/patharanordev/cpulimit/wiki/CPU-Usage-Limiter-for-Linux`.

Usage :

```
sudo cpulimit --limit 80 sh mine.sh
```

##### Bank

You should backup your coin data, example `coinbase`, ...

## Alternative mining

In case you concern about your resources. I recommended `TopMine`. All of the services ( mining, wallet, deposit, withdraw, ... ) are free of charge and are available for everyone. It looks like an investment system. Your miner performance upon `TeraX`.

You can see more detail via link image below :

[![ScreenShot](https://topmine.io/baners/728x90-Rumoviee.gif)](https://topmine.io/?reg=102898)

And other services that provide bitcoin to you look like faucets. I have already test the services below, they payout :

Earn Satoshi free!!!

[![ScreenShot](http://fieldbitcoins.com/img/728x90.gif?v2)](http://fieldbitcoins.com/?ref=qj7kreih306752)

Or solve reCAPTCHA to get reward(bitcoin) by yourself

ClaimBTC

[![ScreenShot](http://claimbtc.com/site/img/ads/promo/300x250.gif)](http://claimbtc.com/?r=52aa8f3aee)

Easy Bitcoin Fuacet

[![ScreenShot](http://easybitcoinfaucet.com/site/img/ads/promo/300x250.gif)](http://easybitcoinfaucet.com/?r=db44e55b85)

Freebitcoin

[![ScreenShot](http://static1.freebitco.in/banners/728x90-3.png)](http://freebitco.in/?r=2590419)

Bitcoin/Litecoin/Dogecoin/Dashcoin Fuacet ( around 190 per 15 minutes )

[![ScreenShot](https://solebtc.com/9c9a89add899721c95293e4ff233c632.gif)](http://solebtc.com/register?referer_id=17171)

Or provide place for advertise :

<a href='https://adbit.co/?r=z9kg2616ieBA552rbRfY34UuwcrDwh'>Adbit.co</a>

<a href='http://a-ads.com?partner=210171'>Advertise with Anonymous Ads</a>

## Donation
If this project help you reduce time to develop, you can give me a cup of coffee :) 

#### Money


[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=A8YE92K9QM7NA)


#### Coin

- Bitcoin  : `1Jiw6aPKskvarnP1rsgJpPv57YqFoAABE1`
- Litecoin : `LcJhc1A13fNJH75Fkiz6CmxwEhu1FFnven`
- Dogecoin : `DTWDxQnirzpef6JN2Www6piiprWN9RjPWd`

