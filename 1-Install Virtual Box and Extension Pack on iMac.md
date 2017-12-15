# Install Virtual Box and Extension Pack on OSX Sierra

Here is a good youtube video on downloading and installing Virtual Box for OSX (ignore the part where he starts installing Windows 10 as we will be installing a different operating system):  https://www.youtube.com/watch?v=rNV5JmxtKP4 

Note: 
* This process assumes you have sudo privs and password.
* And that your downloads are to the ~/Downloads folder unless otherwise specified.

## Steps

1. Download VirualBox for OSX from here https://www.virtualbox.org/wiki/Downloads  (click on the "OSX Hosts" version)
2. At the same time you should download the "VirtualBox 5.2.2 Oracle VM VirtualBox Extension Pack" which you can download from the same page. 
3. This will download two files to your downloads folder
    1. a .DMG file which you will use to install VirtualBox
    2. an Extension Pack file named something like "Oracle_VM_VirtualBox_Extension_Pack-5.2.2-119230.vbox-extpack" (Note these are the version and build numbers as of November 2017.  You should use the numbers based on the files you actually download)
4. Open/Mount the .DMG and double click on the virtualbox.mpkg icon.  Refer to this illustration:  
    ![alt text](http://sites.miis.edu/kb/files/2012/06/VB-02.png "Virtual Box Installation")
5. This will install VirtualBox in your Applications folder
6. To install the extension pack (the youtube video implies it happens automatically but it doesnt!), Do the following in a Terminal Window (I assume you have su priveleges and can supply the admin password when prompted):
```
username:~$ sudo VBoxManage extpack install ~/Downloads/Oracle_VM_VirtualBox_Extension_Pack-5.2.2-119230.vbox-extpack
        # NOTE this is the verion and build number as of November 2017.  The numbers will change over time.  
        #      Use the current numbers from the virtualbox.org download site.
 ```
6. Success will look something like this:
```
 0%...10%...20%...30%...40%...50%...60%...70%...80%...90%...100%
 Successfully installed "Oracle VM VirtualBox Extension Pack".
```
7. And you can check by doing:
```
username:~$ sudo VBoxManage list extpack        
```
8. And you should see the following result: 
```
Password:
Extension Packs: 1
Pack no. 0:   Oracle VM VirtualBox Extension Pack
Version:      5.2.2
Revision:     119230
Edition:      
Description:  USB 2.0 and USB 3.0 Host Controller, Host Webcam, VirtualBox RDP, PXE ROM, Disk Encryption, NVMe.
VRDE Module:  VBoxVRDP
Usable:       true 
Why unusable: 
```
####  Congratulations. Don't you feel accomplished? (I sure as hell do!)

Next we configure a Virtual Machine to Run Debian.  There are two options.  
* Install vanilla Debian downloaded from Debian.org
* Install a Raspberry version of Debian that will run on the AMD64 architecture.
