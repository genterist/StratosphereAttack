1. INSTALLATION OF ARGUS

* Technically can use:
> sudo apt-get update <br/>
> sudo apt install argus-server <br/>
> sudo apt install argus-clients <br/>
* But can do manually :
http://nsmwiki.org/index.php?title=Argus#Download_the_packages
* Note that there are 2 components : server and client
* Note that if there is any complaint about missing files in /usr or any system folder, look for those files in the source of argus (git clone, then use find -name) and copy the files to correct location
<br/>

 2. LAUNCH
  * find the correct interface <br/>
> ip link show
  * launch argus
> sudo argus -d -i [correct interface name] -P 561
* launch ra
> ra -S 127.0.0.1:561
* RA should show logs of package traffics
* CD to root folder of stratosphere
<br/>
  
3. STRATOSPHERE
* Download StratosphereIPS for Linux
> git clone https://github.com/stratosphereips/StratosphereLinuxIPS.git
* launch Stratosphere
> ra -F ./ra.conf -n -Z b -S 127.0.0.1:561 | python2.7 ./slips.py -f ./models -d -v 3

4. ATTACK FRAME WORK
* Download Attack Framework for Linux
> git clone https://github.com/stratosphereips/StratosphereTestingFramework.git
* Install dependencies using PIP with targetted python version (in case you have multiple versions of python running). In this example, we will use PIP2.7
> sudo pip2.7 install prettytable
> sudo pip2.7 install transaction
> sudo pip2.7 install persistent
> sudo pip2.7 install zodb
> sudo pip2.7 install sparse
<br/>  
<br/>  
misc notes:<br/>  
nmcli : disable ethernet interface<br/>  
ssh -XC : to be able to lauch programs with graphical GUI from SSH session<br/>  
