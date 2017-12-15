# Start the VM and Install the OS that you just downloaded
This version assumes we are doing a vanilla Debian install.  The process is similar (use a different netinst iso file) for the Raspbery version

## Recap - At this point you should have:

* Installed VirtualBox on your Host Mac
* `debian-9.3.0-amd64-xfce-CD-1.iso` that you downloaded from RaspberryPi.org sitting in your Downloads folder
* A Debian VM configured in VirtualBox (ideally following the previous instructions in this repository) so you have a window that looks like this:

![Screen9](https://user-images.githubusercontent.com/26580126/33409179-00bd6cce-d548-11e7-8f31-8fa99f4ef14a.png)

### Steps
1. Click the green "Start" arrow in VirutalBox.  This will start your VM.  You will see a window asking you to enter the .iso file that you downloaded (to your Downloads folder)

![DL1](https://user-images.githubusercontent.com/26580126/33412042-2f56bcb6-d557-11e7-9fdb-00dfb483a638.png)

2. Click on the folder icon with the green up arrow.  This will open your finder and let you select the .iso file you downloaded:

![DL2](https://user-images.githubusercontent.com/26580126/34025978-f2296e9e-e120-11e7-8c2b-2dcaa81b4812.png)

3. Select the .iso file and click "Start"

![DL3](https://user-images.githubusercontent.com/26580126/33412087-5ee2c15a-d557-11e7-9fc7-ac3046b8a2ec.png)

4. The installer will start and you will see the following:

![DL4](https://user-images.githubusercontent.com/26580126/33412119-7a878b16-d557-11e7-99bf-8b29125d8ae1.png)

5. Select "Graphical install" (you can experiment but then you're on your own)

![DL5](https://user-images.githubusercontent.com/26580126/33412139-8f35b696-d557-11e7-91b0-f5fc74261f79.png)

6. Select your keyboard (I'm using American English) and click "Continue".

7. The system will then take you through a series of disk partitioning steps.  Just follow along:

![DL6](https://user-images.githubusercontent.com/26580126/33412190-de333dfe-d557-11e7-8ace-806de8f5e155.png)

We are using the entire disk because its easy and I am NOT a linux geek

![DL7](https://user-images.githubusercontent.com/26580126/33412200-eca41d36-d557-11e7-95da-dfc783bbbfc2.png)

This is a scary window, but VirtualBox has already allocated this space from your free OSX disk space, so you will not be clobbering anything on your iMac.  Hit Continue.

![DL8](https://user-images.githubusercontent.com/26580126/33412206-fc411f50-d557-11e7-9ac2-8d34cc73eacf.png)

Put all files in one partition because we (and by we I mean "I") are new users

![DL9](https://user-images.githubusercontent.com/26580126/33412221-1070faa4-d558-11e7-92a4-1bdcf297fba1.png)

Yes, we REALLY want you to write the changes to disk.  Hit Continue.

![DL10](https://user-images.githubusercontent.com/26580126/33412238-23d40320-d558-11e7-8ac1-19ded77c43a6.png)

**YES, WE REALLY REALLY WANT THE CHANGES WRITTEN TO DISK **  Hit Continue.

![DL11](https://user-images.githubusercontent.com/26580126/33412298-773a8412-d558-11e7-8eee-35ec95305c56.png)

Now the system will install (this may be out of order with the next two screenshots. I can't remember)

![DL12](https://user-images.githubusercontent.com/26580126/33412318-90d41d8e-d558-11e7-8177-0bc675de972e.png)

Yes, we want to install the bootl loader on the MBR of our virtual disk so the VM will boot automatically from now on.  Click Continue

![DL13](https://user-images.githubusercontent.com/26580126/33412339-a27dccb0-d558-11e7-826f-528bc86b3818.png)

...And lets install the boot loader where the wise installer suggests.  Hit Continue.

![DL14](https://user-images.githubusercontent.com/26580126/33412356-c0dcf078-d558-11e7-96da-d608376b6977.png)

...Hit continue here and...(drum roll please)

![DL15](https://user-images.githubusercontent.com/26580126/33412369-d72887a2-d558-11e7-82c3-e0aa593ab899.png)

Ta..Da.. Your very own Raspberry Pi desktop running on a VM on your iMac

## But Wait...There's more...

Before you can do useful things, like share files between your iMac and VM, or cut and paste, or drag and drop, you need to install something called VirtualBox Guest Additions (not to be confused with VirtualBox Extension Pack).  The Guest additions get installed into your Guest Operating System (Debian in this case).

But that is another Chapter...


