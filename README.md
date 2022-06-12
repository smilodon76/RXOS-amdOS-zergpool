RXOS MINING OS for amd gpus

eth mining is coming to an end and mining with multialgo switch will return to the most profitable.

version 3.4.1is preloaded on phoenixminer.dont usage in ARGS.

changelog

changing algo switch algorithm for better shares per day on most algo in zergpool

add ubqhash algo on zergpool

changing in profitability calculation with very realistic data.the miner in zergpool will not work if the energy cost is above profitability. also after 5 minutes and while the miner does not work due to negative profits,The rig will be deactivated for a period of time 10000sec. When it is auto activated again it will check if the profitability is above the energy cost and will act accordingly.

Download link https://drive.google.com/drive/folders/1ZMJ7LENK5QTchnTLKzmKruas1PqLPvld?usp=sharing

this is the only genuine download link. Anything else you avoid downloading.

The operating system is very easy, simple and light and is addressed to those who know what mining is, know how to copy an img file to usb, ssd and hdd, have basic knowledge of linux terminal, ssh, nano, computer ip finding and is oriented to long-term durability of graphics cards.

USE IT AT YOUR OWN RISK.

# is free to use and do not have fees.

It does not have a graphic environment.working only local with ssh.
It does not have a monitoring.all ports in firewall its closed.

Based on ubuntu server 18.04 kernel 4.17 & amdgpu-pro 20.40.

Minimum requirements 8gb usb, hdd, (no tested ssd) 2gb ram.Amd gpus rx460/470/480/550/560/570/580/590 2-4-8gb and up no tested rxvega rx5000xt rx6000xt.

support up to 6 gpus with overclocking and auto fancontrol.

all edits are done with the nano word processor

for save on nano ctrl+x after y and enter. for cancel ctrl+c.

write the img and browse to your computer with windows,find disk 'rxos-conf'.change parameters on miner.conf and overclock settings on set-oc.conf set-ocB.conf and set-ocC.conf is useful only in zergpool.

boot the rig and connect via ssh
user:rxos
pass:1

if you want change password with $ sudo passwd rxos

for all commands type $ rxos-help

# For ZERGPOOL algo switching profit

first modify bios and set overclocks with the guides listed in the download link for low power usage and efficiency.

13 algos supported cryptonight_gpu cryptonight_haven equihash125 equihash144 equihash192 etchash ethash firopow heavyhash kawpow skein2 ubqhash verthash

type $ conf and write on globalminer zergpool GLOBALMINER=zergpool

paste your wallet on ZWALLET= and coin payout to PAYCOIN=

do not add the parameter ID= to passwd . it already exists with the hostname of each mining rig.

type $ zbenches and change your all AVERAGE gpus hashrate.change it and on the fly.

if you do not want to mining an algorithm comment the hashrate with 0# in benches.example zergpool-verthash 0#493

type $ zwatts and change AVERAGE power consuption for all gpus on wall.for 225watt type 225 for 1230watt type 1230 .change it and on the fly

type $ zprice and change if you want the price of the KWh in your country.default 0.1

if you want you do not change the benches and watts. it will work satisfactorily but have high power usage.default hashrates and watts they correspond in one rx470 8gb micron memory.

save and type $ allow to start miner.

change the hashrate in the same format. otherwise the profitability will not work properly. if there is a big discrepancy between the calculated and the real profit, it is because the hashrate is not enough to find blocks in a reasonable time. the more they use this operating system the closer the profits will be to the estimated.

if you want to make changes to the zerpool and the profitability is low, so that the rig is not deactivated, type disallow && minestop

in zergpool the profitability seen in the output of the miner is calculated with the api  earnings-power usage cost. if you do not want to subtract the energy consumption in zwatts mwatts put all the algorithms to 0.

If an algo has problems connecting to zergpol comment the hashrate with 0# for a few hours or days until it comes back.

if the api does not work properly, the miner will work with the last algorithm in alphabetical order, which is currently verthash or zero (no work miner).

 the miner in zergpool will not work if the energy cost is above profitability. also after 5 minutes and while the miner does not work due to negative profits,The rig will be deactivated for a period of time 10000sec. When it is auto activated again it will check if the profitability is above the energy cost and will act accordingly.
 
 never put 0 watts in an algorithm. put 0 in everything except zergpool-zero only if you do not want the cost of electricity to be calculated.

in zbenches zwatts do not make any changes to zergpool-zero.

# for other coins and pools

type $ conf and write on globalminer lolminer or phoenixminer or teamredminer or xmr-stak

example

GLOBALMINER=phoenixminer

ARGS='-proto 1 -gt 25 -coin etc' <== all arguments inside quotes.

POOL=etc.2miners.com:1010

WALLET=wallet_here

PASS=x

save and type $ minestop to restart miner

this configs (-log 0 -amd -acm -mi 14 -astats 1 -rmode 1 -rxboost 1) is preloaded on phoenixminer.dont usage in ARGS.

# overclocking

# be careful what you do may damage your cards.
 
for overclocking read the guides listed in the download link

if you notice a problem, tell me to fix it. overclocking has not been tried extensively with many cards because I only have one card.

the miner automatically restarts every 10000 seconds to minimize the risk of a card freezing. the system restarts automatically every week

It has atiflash for bios change. We type $ sudo atiflash -h.

It has amdgpu-fancontroler automatic, the fans do not operate below 40 degrees.

It has amdmemtweak for changing straps while the rig works. Type $ sudo amdmemtweak --help

It has amdmeminfo for graphics card memory information, we type $ gpus.

It has wifi but working only with 802.11g adapters.with 802.11n the rxos freezes.type $ wifi ,change ssid and password and reboot the rig.

It has a samba server to access the /home/rxos folder and the path is on linux smb://localhost/rxos  and on windows smb:\\localhost\rxos userpass is the same rxos and 1.

Τhe operating system does not update automatically. you need to download the latest version and copy all the configs from the older one. miner-conf set-oc.conf set-ocB.conf set-ocC.conf

if adding more gpus after first run type $ clean-xmr-stak to remove xmr-stak older configs.

if you have 2gb gpus type $ zbenches and put hashrate to 0, equihash125 equihash192 etchash ethash firopow kawpow.

if you have 4gb gpus type $ zbenches and put hashrate to 0, equihash192 firopow

updating miners only manualy.download new version of phoenixminer teamredminer lolminer and wildrig-multi,copy via usb on partition rxos-conf or with samba.
type $reload-miners  and after $minestop to restart miner

If you like it and use it permanently please make a donation to upload new editions.

BTC: bc1qfevx3dv3ctye8xnrxt4mpau4qmuxeqepl8dgqcfqs47p7klck3pqd7ulvw

