# RXOS MINING OS for amd gpus with zergpool multialgo switch #


Download img https://drive.google.com/drive/folders/1ZMJ7LENK5QTchnTLKzmKruas1PqLPvld?usp=sharing


# version 1.2
changelog

add zergpool.com multialgo switching profit.Supported algos ethash, etchash, kawpow, ubqhash, verthash.

add auto-hostname on boot

add straps --ref 25 on boot

The operating system is very easy, simple and light and is addressed to those who know what mining is, know how to copy an img file to usb, ssd and hdd, have basic knowledge of linux terminal, ssh, nano, computer ip finding and is oriented to long-term durability of graphics cards.

 USE IT AT YOUR OWN RISK.

It does not have a graphic environment.

Based on ubuntu server 18.04 kernel 4.17 & amdgpu-pro 19.50.
Minimum requirements 8gb usb, hdd, (no tested ssd) 2gb ram and up for ethash, 3gb and up for zergpool,verthash.Amd gpus rx460/470/480/550/560/570/580,rxvega and those who support amdgpu-pro 19.50

For zergpool and verthash it is recommended to use hdd, ssd because the verthash.dat file that you create when you first run in the /home/rxos/.miners path delays the start of the miner and in some cases if you use usb it may crash.

The first boot may be delayed.

# For zergpool algo switching profit #

first type $ minestop to stop miner.

Step 1: enter $ nano wallet.conf and change the wallet and payment currency. Leave the worker as is.

Step 2: type $ nano benches and change the hashrate of gpus only in the algorithms Ethash, etchash, kawpow, ubqhash, verthash in the same format.For ethash algos 50.5Mhs type 50.500,for kawpow 15.3Mhs type 15300, for verthash 300hs type 300 and for 1.5Khs type 1500.

If you have graphics cards with 2gb vram put ethash, etchash, kawpow to 0 because these cards can not mining them. If you do not want to mining an algorithm put 0.

to save type ctrl + x then y and enter.

Step 3: type $ autominer and the mining will start automatically at the start of the rig you do not need to do anything else. Type $ miner for miner-output.

# for other coins and pools #

first type $ minestop to stop miner.

With the $ ls command we see executables that exist and correspond to each miner phoenixminer.sh, teamredminer.sh, lolminer.sh. I explain the procedure for phoenixminer which is the same for all miners.

$ nano phoenixminer.sh and we process the login details in the mining pool without disturbing the miners' routes or the existing settings.

#! / bin / bash

source /home/rxos/wallet.conf

cd /home/rxos/.miners/phoenixminer

./PhoenixMiner

You leave this information as it is, otherwise the miner will not work.

to save type ctrl + x then y and enter.

To check if it works, type $ sudo ./phoenixminer and if all goes well, stop it with ctrl + c. Then type $ phoenixminer and the mining will start automatically at the start of the rig, you do not need to do anything else.

To check if the miner works, type $ miner

To stop the miner type $ minestop.

To restart the miner enter the name of eg phoenixminer

To change miner enter the name of eg lolminer.

To restart the rig, enter $ r. To deactivate $ off.

All miners run with an administrator account.

It has no monitoring. Access is only available to a local network via ssh for security and has a firewall enabled.

It has underclocking with the commands $ dpm7, dpm6, dpm5, dpm4, dpm3 for the power state gpu (default on img dpm5) without the need to restart. The autominer for zergpool.com has dpm set for each algorithm. Currently not supported different dpm for each card.
After restarting do not disable underclocking, we must change it whenever we want. To reset the clocks type $ resetoc.

Overclocking is possible through from the miner, first we type $ resetoc and then we start the miner with overclocking settings.

It has wifi type $ nano wifi.txt for instructions.

It has atiflash for bios change. We type $ sudo atiflash -h.

It has amdgpu-fancontroler automatic, the fans do not operate below 40 degrees.

It has amdmemtweak for changing straps while the rig works. Type $ sudo amdmemtweak --help

It has amdmeminfo for graphics card memory information, we type $ amdmeminfo.

It has a samba server to access the /home/rxos folder. We type $ samba to activate it for 2.5 hours and the path is smb: // hostname / Homes /

The hostname is located on the top right of ssh motd.

The miner operates for about 4 hours and stops automatically for 2.5 minutes to extend the life of the cards.

Every 7 days it goes off completely for 15 minutes and you restart on your own ..

To check the system temperatures we type $ sensors.

To check temperatures and statistics for graphics cards type $ gpu, gpu1, gpu2 .... to gpu9, one card at a time and end with ctrl + c.

The operating system has a very low devfee 1 thread on the cpu for a few minutes every 3 hours. It does not interfere with gpu mining.

Never upgrade to a newer version because it will stop working.

The miners are in the path /home/rxos/.miners.

To upgrade the miners requires a short process. Via samba copy and replace the new version of the miner in the /home/rxos/.miners folder and then $ sudo chmod +x /home/rxos/.miners/*

For maintenance type $ maintenance && sudo cleanup.sh

If you do any damage to the operating system, copy img again.

username: rxos
pass: 3826

If there is a response I will upload a new version with more miners and algos in zergpool.

