# Inst-RPI-in-VirtualBox-Mac
Installing Raspberry Pi Desktop in Virtual Box on Mac OS X Sierra

OK so I am trying to learn some new stuff and thought it would be a good idea to start to document it to the best of my ability.
There are two reasons for this
1)  So I have a reference for the future
2)  In the unlikely event someone else might try some of this stuff with the same limited knowledge I have.
I have found that while there is A SHIT TON of information about Raspberry PI and the RPI desktop, and Virtual Box and OpenHAB2 which are all interests of mine, they are not all clear and quite often conflict with each other.  Now recognize it has been a long time since I got into the details of stuff at this level so I'm not criticizing anyone who puts information out.  I'm just trying to organize in a way that makes sense for me.

## My Config
* iMac 27 inch, Mid 2010
* 2.93 Ghz Intel Core I7
* 16GB 1333 Mhz DDR3
* Startup disk 250 GB SSD (>100GB available -- probably can get by with less than this, I'm only setting up a 30-40GB VM storage)

## Steps
1. Install Virtual Box on OSX Sierra.  Here is a good youtube video on downloading and installing Virtual Box for OSX (ignore the part where he starts installing Windows 10 as we will be installing a different operating system):  https://www.youtube.com/watch?v=rNV5JmxtKP4 
    1. Download VirualBox for OSX from here https://www.virtualbox.org/wiki/Downloads  (click on the "OSX Hosts" version)
    2. At the same time you should download the "VirtualBox 5.2.2 Oracle VM VirtualBox Extension Pack" which you can download from the same page. (Note: I assume that both VirtualBox and the Extension Pack have been downloaded to your iMac Downloads folder)
    3. This will download two files to your downloads folder
        1. a .DMG file which you will use to install VirtualBox
        2. an Extension Pack file named something like "Oracle_VM_VirtualBox_Extension_Pack-5.2.2-119230.vbox-extpack"
    4. Open/Mount the .DMG and double click on the virtualbox.mpkg icon.  Refer to this illustration:  
    ![alt text](http://sites.miis.edu/kb/files/2012/06/VB-02.png "Virtual Box Installation")
    4. This will install VirtualBox in your Applications folder
    5. To install the extension pack (the youtube video implies it happens automatically but it doesnt!), Do the following in a Terminal Window (I assume you have su priveleges and can supply the admin password when prompted):
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
        username:~ TomsIMac$ sudo VBoxManage list extpacks
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

        
2. Download Raspberry Pi desktop from RaspberryPi.org
3. Create Virtual Box with debian raspberry pi desktop
4. Make sure you have additions installed 
5. Confirm that cut/paste and drag/drop work between Vbox and OSX
