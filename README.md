# rtl8814AU
Realtek 8814AU USB WiFi driver.

Forked from [Diederik de Haas](https://github.com/diederikdehaas/rtl8814AU)'
repository which is based on version 4.3.21 of an Edimax driver for the
EW-7833UAC device.

Updated with support for kernels >= 4.14.

# DKMS support

From your src dir

````
sudo cp -R . /usr/src/rtl8814au-4.3.21
sudo dkms build -m rtl8814au -v 4.3.21
sudo dkms install -m rtl8814au -v 4.3.21
````

This should keep your 8814AU adapter working post kernel updates.


Moved to networking and wireless
I just found one that installs
Code:
```
sudo apt-get update && sudo apt-get install git dkms
dont use this line, but use following line :git clone https://github.com/zebulon2/rtl8814au.git
git clone https://github.com/su3010/rtl8814au.git
cd rtl8814au
gedit dkms.conf
```
Replace line 1 MAKE="'make'" with
Code 
```
folloiwng line  is not required. repository has this change.
MAKE="'make' all KVER=${kernelver}"
```
save and exit gedit, then
Code:
```
cd 
sudo dkms add ./rtl8814au
sudo dkms install rtl8814au/4.3.21
```
Reboot
