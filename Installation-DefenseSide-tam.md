1. INSTALLATION OF ARGUS
* Technically can use:
> sudo apt install argus
> sudo apt install argus-clients
* But can do manually :
http://nsmwiki.org/index.php?title=Argus#Download_the_packages
* Note that there are 2 components : server and client
* Note that if there is any complaint about missing files in /usr or any system folder, look for those files in the source of argus (git clone, then use find -name) and copy the files to correct location

2. LAUNCH
* find the correct interface
> ip link show
* launch argus
> argus -d -i <correct interface name> -P 561
* launch ra
> ra -S 127.0.0.1:561
* RA should show logs of package traffics
* CD to root folder of stratosphere
*launch Stratosphere
> ra -F ./ra.conf -n -Z b -S 127.0.0.1:561 | python2.7 ./slips.py -f ./models -d
  
  
misc notes:
nmcli : disable ethernet interface
