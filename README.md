RXOS MINING OS for amd gpus

eth mining is coming to an end and mining with multialgo switch will return to the most profitable.

version 3.3.3 minor fixes  

Download img https://drive.google.com/drive/folders/1ZMJ7LENK5QTchnTLKzmKruas1PqLPvld?usp=sharing

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

write the img and browse to your computer with windows,find disk 'rxos-conf'.paste all your wallets on wallets conf,globalminer on miner-conf and overclock settings on set-oc.set-ocB and set-ocC is useful only in zergpool.

boot the rig and connect via ssh
user:rxos
pass:1

change password with $ sudo passwd rxos

for all commands type $ rxos-help

type $ wallets and paste your coin wallets btc eth rvn etc,zergpool and payout coin for zergpool

# For zergpool algo switching profit

10 algos supported cryptonight_gpu cryptonight_haven equihash125 equihash144 equihash192 etchash ethash firopow kawpow verthash

type $ conf and write on globalminer zergpool GLOBALMINER=zergpool

type $ zbenches and change your gpus hashrate.change it and on the fly.

if you do not want to mining an algorithm set its hashrate to zero. example zergpool-etchash 0

type $ zwatts and change power consuption for all gpus on wall.for 225watt type 0.225 for 1230watt type 1.230.change it and on the fly

if you want you do not change the benches and watts. it will work satisfactorily.default hashrates and watts they correspond in one rx470 8gb micron memory.

save and type $ allow to start miner.

change the hashrate in the same format. otherwise the profitability will not work properly. if there is a big discrepancy between the calculated and the real profit, it is because the hashrate is not enough to find blocks in a reasonable time. the more they use this operating system the closer the profits will be to the estimated.

if you do not want to mining an algorithm put hashrate 0 in zbenches. you can leave only 1 algorithm and only it will work.

do not add the parameter ID= to passwd. it already exists with the hostname of each mining rig.

in zergpool the profitability seen in the output of the miner is calculated with the zergpool api  earnings-power usage cost. if you do not want to subtract the energy consumption in zwatts put all the algorithms to 0

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

if you notice a problem, tell me to fix it. overclocking has not been tried extensively with many cards because I only have one card.


It has atiflash for bios change. We type $sudo atiflash -h.

It has amdgpu-fancontroler automatic, the fans do not operate below 40 degrees.

It has amdmemtweak for changing straps while the rig works. Type $sudo amdmemtweak --help

It has amdmeminfo for graphics card memory information, we type $gpus.

It has a samba server to access the /home/rxos folder and the path is on linux smb://localhost/rxos  and on windows smb:\\localhost\rxos userpass is the same rxos and 1.

Τhe operating system does not update automatically. you need to download the latest version and copy all the configs from the older one. miner-conf wallets set-oc set-ocB set-ocC

if adding more gpus after first run type $ clean-xmr-stak to remove xmr-stak older configs.

if you have 2gb gpus type $ zbenches and put hashrate to 0 equihash125 equihash192 etchash ethash firopow kawpow.

if you have 4gb gpus type $ zbenches and put hashrate to 0 equihash192 firopow

updating miners only manualy.download new version of phoenixminer teamredminer and lolminer,copy via usb on partition rxos-conf or with samba.
type $ reload-miners and $ minestop to restart miner.

donate: bc1qfevx3dv3ctye8xnrxt4mpau4qmuxeqepl8dgqcfqs47p7klck3pqd7ulvw

Καλά κέρδη.
