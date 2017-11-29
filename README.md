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
    2. At the same time you should install the "VirtualBox 5.2.2 Oracle VM VirtualBox Extension Pack" which you can download from the same page.
    3. This will download a .DMG file to your downloads folder.  Open/Mount the .DMG and double click on the virtualbox.mpkg icon.  Refer to this illustration:  http://sites.miis.edu/kb/files/2012/06/VB-02.png
    4. This will install VirtualBox in your Applications folder
    5. **Watch Out #1**
        1. The video and instructions imply that the VirtualBox 5.2.2 Oracle VM VirtualBox Extension Pack" gets installed automatically when you install VBox.  It doesnt.  Heres how to check
        2. In a terminal window run the following command `username:~$ sudo VBoxManage list extpack` and check the result
        3. If the result is `Extension Packs: 0` then the extension pack has not been loaded!
        4. To ACTUALLY load the extension pack, do the following in a terminal window (be sure to copy the whole line):
 ```
    username:~$ wget http://download.virtualbox.org/virtualbox/5.2.2/Oracle_VM_VirtualBox_Extension_Pack-5.2.2-119230.vbox-extpack
 ```    5. Once downloaded do this:
    ```
        username:~$ sudo VBoxManage extpack install Oracle_VM_VirtualBox_Extension_Pack-5.2.2-119230.vbox-extpack
        # NOTE this is the verion and build number as of November 2017.  The numbers will change over time.  
        #      Use the current numbers from the virtualbox.org download site.
    ```
2. Download Raspberry Pi desktop from RaspberryPi.org
3. Create Virtual Box with debian raspberry pi desktop
4. Make sure you have additions installed 
5. Confirm that cut/paste and drag/drop work between Vbox and OSX
