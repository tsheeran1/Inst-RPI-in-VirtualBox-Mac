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

![DL3](https://user-images.githubusercontent.com/26580126/34026689-c5c29722-e125-11e7-8db5-2ea4d806fa4c.png)

4. The installer will start and you will see the following:

![DL4](https://user-images.githubusercontent.com/26580126/34026747-21cd3522-e126-11e7-98f7-4e30036ebbe8.png)

5. Select "Graphical install" (you can experiment but then you're on your own)

6. At this point the installer will ask you to select a series of options (I dont have screen shots for each):  
* Language - I pick English
* Location - I pick United States
* Keyboard - I pick American English

7. The system will then ask you to select your network controller.  My system only has one so its easy (sorry no screenshot here)

8. Next you will be asked to name your system.  The installer suggests debian which is fine with me.  See below.

![DL16](https://user-images.githubusercontent.com/26580126/34026934-73e3eea4-e127-11e7-9659-0cfe1e0c5cef.png)

9. Next you will be asked for your local domain.  Mine is .lan because I think thats what the router sets up.  
Don't really know why but when I do a `hostname` on my Mac for any IP in my house they all comeback with systemname.lan.  
Fill in yours.

10. The system will ask you to set up a password for `root`.  
Then ask you to set up a user and password. 
Do so.

11. The system will ask you to select a time zone.  I pick Eastern.  Pick yours.

12. The system will then take you through a series of disk partitioning steps.  Just follow along:

![DL6](https://user-images.githubusercontent.com/26580126/34027203-3416b458-e129-11e7-87f1-12f7e901ec8b.png)

  1. Select "Guided - use entire disk" because I am not a linux geek
  2. The next window asks you to select the disk you want.  For relative newbs there should be only one.  Pick it.  
Note it has some scary language about erasing everything on the disk.  
Remember this is the 20GB disk you set up in VirtualBox which I why you need the 20GB free space on your Host Mac.  
It's not going to erase random files on your Mac  
  3. The next window asks how you want to partition the disk.  
Select the option to put all files in one partition because we (and by we I mean "I") are new users  
  4. The next window asks if you want to finish and partition the disk.  You do.  
  5. The next window asks if you're really really sure you want to write the partitions to the disk.  You do.

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


