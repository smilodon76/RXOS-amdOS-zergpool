RXOS MINING OS for amd gpus

Download img https://drive.google.com/drive/folders/1ZMJ7LENK5QTchnTLKzmKruas1PqLPvld?usp=sharing

The operating system is very easy, simple and light and is addressed to those who know what mining is, know how to copy an img file to usb, ssd and hdd, have basic knowledge of linux terminal, ssh, nano, computer ip finding and is oriented to long-term durability of graphics cards.

USE IT AT YOUR OWN RISK.

It does not have a graphic environment.working only local with ssh.
It does not have a monitoring.all ports in firewall its closed.

Based on ubuntu server 18.04 kernel 4.17 & amdgpu-pro 20.40.

Minimum requirements 8gb usb, hdd, (no tested ssd) 2gb ram.Amd gpus rx460/470/480/550/560/570/580/590 4gb and up no tested rxvega rx5000xt rx6000xt.

support up to 6 gpus with overclocking and auto fancontrol.

all edits are done with the nano word processor

write the img and brwse to your computer with windows,find disk 'rxos-conf'.paste all your wallets on wallets conf.
boot the rig and connect via ssh
user:rxos
pass:1

for all commands type $ rxos-help

type $ wallets and paste your coin wallets btc eth rvn etc,zergpool and payout coin

# For zergpool algo switching profit

7 algos supported cryptonight_gpu cryptonight_haven etchash ethash firopow kawpow verthash

type $ conf and write on globalminer zergpool GLOBALMINER=zergpool

type $ zbenches and change your gpus hashrate.change it and on the fly.

type $ zwatts and change power consuption for all gpus on wall.for 225watt type 0.225 for 1230watt type 1.230.change it and on the fly

if you want you do not change the benches and watts. it will work satisfactorily.default hashrates and watts they correspond in one rx470 8gb micron memory.

save and type $ allow to start miner.

# for other coins and pools

type $ conf and write on globalminer phoenixminer or teamredminer

example

GLOBALMINER=phoenixminer

ARGS='-amd -acm -mi 14 -gt 25' <== all arguments inside cuotes

POOL=eth.2miners.com:2020

WALLET=$ETHWALLET <== source from  wallets conf

PASS=x

save and type $ minestop to restart miner

# overclocking

# be careful what you do may damage your cards.

type $ set-oc and write your gpu oc clocks 
example for gpu 0 and 1

#gpu core settings#        

cclock0=1100    cclock1=1150    cclock2=    cclock3=    cclock4=    cclock5=
cmv0=875        cmv1=900        cmv2=        cmv3=        cmv4=        cmv5=                     
dpm0=07         dpm1=07         dpm2=         dpm3=         dpm4=         dpm5=                
                    
#gpu vram settings#

mclock0=1900    mclock1=1950    mclock2=    mclock3=    mclock4=    mclock5=
mmv0=875        mmv1=900        mmv2=        mmv3=        mmv4=        mmv5=

REF=100

save and type $ apply-oc

if there is interest and donations I will upload a newer version with overclocking mods nicehash and miningpoolhub algo switch

donate: bc1qfevx3dv3ctye8xnrxt4mpau4qmuxeqepl8dgqcfqs47p7klck3pqd7ulvw
