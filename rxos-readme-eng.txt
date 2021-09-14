RXOS MINING OS

The operating system is very simple and light and is addressed to those who know what mining is, know how to copy an img file to usb, ssd and hdd, have basic knowledge of linux terminal, ssh, nano, computer ip finding, etc.

USE IT AT YOUR OWN RISK.

It does not have a graphical interface.

Based on ubuntu server 18.04 kernel 4.17 & amdgpu-pro 19.50.
Minimum requirements 8gb usb, hdd. (No tested ssd) 1gb ram and up for ethash, 2-3gb and up for verthash.Amd rx4XX, rx5XX graphics cards and those supported by the driver amdgpu-pro 19.50

Download img https://drive.google.com/drive/folders/1ZMJ7LENK5QTchnTLKzmKruas1PqLPvld?usp=sharing

After unzipping it, copy it and start the operating system, login or via ssh from another computer with username: rxos ​​& pass: 3826.
The mining will start working for me, to check if it works properly we type $ miner and if all the cards that are required work, we type $ minestop to stop.
With the $ ls command we see executables that exist and correspond to each miner phoenixminer.sh, teamredminer.sh, ethminer.sh. I explain the procedure for phoenixminer which is the same for all miners.
$ nano phoenixminer.sh and we process the login details in the mining pool without disturbing the miners' routes or the existing settings.
#! / bin / bash
cd /home/rxos/.miners/phoenixminer
./PhoenixMiner
You leave this information as it is, otherwise the miner will not work.

To check if it works type $ sudo ./phoenixminer and if all goes well stop it with ctrl + c. Then type $ phoenixminer the mining will start automatically at the start of the rig you do not need to do anything else.For miner output type $ miner .
Avoid overclocking so that the rig does not get stuck. It is set to restart the miner as a service if something goes wrong but with excessive overclocking, if a card gets stuck it will need a manual restart to come back.

To stop the miner type $ minestop.
To restart the miner enter the name of eg phoenixminer
To change miner we simply type the name of eg teamredminer
To restart the rig, type $ r. To deactivate $ off

All miners run with an administrator account.

It has monitoring only on localhost through the api of the respective miner at door 3333.

It has underclocking through the miner as well as with the commands $ dpm7, dpm6, dpm5, dpm4, dpm3 for the power state gpu (default on img dpm4) and mdpm2, mdpm1 for gpu-vram (default mdpm2) without the need to restart. restart NOT turn off overclocking, we must change it whenever we want. To reset clocks type $ resetoc.

It has wifi we type $ nano wifi.md for instructions.
It has atiflash for bios change. We type $ sudo atiflash -h
It has amdgpu-fancontroler automatic, the fans do not operate below 40 degrees.
It has amdmemtweak for changing straps while the rig works. Type $ sudo amdmemtweak --help
It has amdmeminfo for graphics card memory information, we type $ amdmeminfo.
It has a samba server to access the /home/rxos folder. We type $ samba to activate it for 2.5 hours and the path is smb: //localhost/Homes/
The miner operates for about 4 hours and stops automatically for 2,5 minutes to extend the life of the cards.
Every 7 days you restart on your own ..
To check the system temperatures we type $ sensors 
To check temperatures and statistics for graphics cards type $ gpu, gpu1, gpu2 .... to gpu9, one card at a time and end with ctrl + c.

It has no hidden charges and fees except from the miners.
The miners are in the path /home/rxos/.miners.
Never upgrade the operating system to a newer version. Just upgrade to security programs and updates.
To upgrade the miners requires a short process. Via samba copy and replace the new version of the miner in the /home/rxos/.miners folder and then $ sudo chmod + x /home/rxos/.miners/*
For maintenance type $ maintenance && sudo cleanup.sh
Sudo cleanup.sh deletes the verthash.dat file located in the default path /home/rxos/.cache/minerdata, useful in case it does not work properly.
If you do any damage to the operating system, copy img again.

username: rxos
pass: 3826
If you liked it and use it constantly please make a donation.

Bitcoin BTC: bc1qyvekv9vxcsc7lxfn4g2z87dxdw70y5mer9furgg3gqw8y2y5pf3s836wrz

If there is a response I will upload a new version with more miners.
