RXOS MINING OS for amd gpus

Download img https://drive.google.com/drive/folders/1ZMJ7LENK5QTchnTLKzmKruas1PqLPvld?usp=sharing

The operating system is very easy, simple and light and is addressed to those who know what mining is, know how to copy an img file to usb, ssd and hdd, have basic knowledge of linux terminal, ssh, nano, computer ip finding and is oriented to long-term durability of graphics cards.

USE IT AT YOUR OWN RISK.

It does not have a graphic environment.

Based on ubuntu server 18.04 kernel 4.17 & amdgpu-pro 20.40.
Minimum requirements 8gb usb, hdd, (no tested ssd) 2gb ram.Amd gpus rx460/470/480/550/560/570/580 no tested rxvega rx5000xt rx6000xt.

boot the rig and connect via ssh
user:rxos
pass:1
# For zergpool algo switching profit
type $ conf and write on globalminer zergpool example GLOBALMINER=zergpool 
savetype $wallets and paste your zergpool wallet and payout coin.
save and type allow to start miner.

# for other coins and pools

type $ conf and write on globalminer phoenixminer or teamredminer
example
GLOBALMINER=zergpool
ARGS='-a ethash'
POOL=eth.2miners.com:2020
WALLET=$ETHWALLET   --> from paste in wallets
PASS=x
save and type minestop to restart miner




To res
