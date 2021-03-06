# Start the VM and Install the OS that you just downloaded
This version assumes we are doing a vanilla Debian install.  The process is similar (use a different netinst iso file) for the Raspbery version

## Recap - At this point you should have:

* Installed VirtualBox on your Host Mac
* `debian-9.3.0-amd64-xfce-CD-1.iso` that you downloaded from Debian.org sitting in your Downloads folder
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

<ol><ol><ol>
  <li>Select "Guided - use entire disk" because I am not a linux geek
  <li>The next window asks you to select the disk you want.  For relative newbs there should be only one.  Pick it.
    <ul><ul>
      <li>  Note it has some scary language about erasing everything on the disk.</li>
      <li>  Remember this is the 20GB disk you set up in VirtualBox which is why you need the 20GB free space on your Host Mac.</li>
      <li>  It's not going to erase random files on your Mac</li>
      </ul></ul>
  <li>The next window asks how you want to partition the disk.  
  Select the option to put all files in one partition because we (and by we I mean "I") are new users
  <li>The next window asks if you want to finish and partition the disk.  You do.
  <li>The next window asks if you're really really sure you want to write the partitions to the disk.  You do.
  </ol></ol></ol>

13. The installer will then indicate it is installing the base system.

14. After the base system is installed the installer will ask if you want to use a mirror.  Assuming you have a decent internet connection, you do.

16. The installer will ask if you have a proxy server it needs to deal with for the mirror.  I don't so I leave blank and continue.

17. The installer asks if you want to install additional sofware from the mirror:
![DL11](https://user-images.githubusercontent.com/26580126/34028601-366420f2-e132-11e7-91b5-f4c977e0569a.png)

<ul><ul>
  <li>Debian desktop environment, Xfce, print server and standard system utilities are already checked.
  <li>I also checked SSH server and web server (not show in the above screenshot)
  <li>Once you click "continue" the installation of the additional packages will take a few minutes.
  </ul></ul>

18. The installer will ask if you want to install the GRUB boot loader in the master boot record of your VM hard disk.  You do.

![DL12](https://user-images.githubusercontent.com/26580126/34029310-d111ee60-e135-11e7-9b3b-75ccfa770033.png)

19. It will then ask you to select the disk you want to install GRUB on.  Don't opt to manually enter.  There is only one. Select the option it presents you.

![DL13](https://user-images.githubusercontent.com/26580126/34029236-6c6012c6-e135-11e7-9cc7-f78116135618.png)

20. At this point, the installer will tell you it is complete.  Hit continue.

![DL14](https://user-images.githubusercontent.com/26580126/34029340-0c0c744a-e136-11e7-89e4-c7c35792bf97.png)

21.  The operating system will install and launch the XFCE gui prompting you to login.  Enter the credentials you set up in step 10.

![DL15](https://user-images.githubusercontent.com/26580126/34029432-9d901728-e136-11e7-94e1-3c9855376f07.png)

22.  The system logs you in.  Your first login will prompt you to select a blank panel or the default panel.  I pick default. (not shown on screenshot below.  And you are now logged into Debian v9.3 running in a VM on your Mac!!

![DL16](https://user-images.githubusercontent.com/26580126/34029554-305f9740-e137-11e7-8ccf-25a0977a3ed5.png)

## But Wait...There's more...

Before you can do useful things, like share files between your iMac and VM, or cut and paste, or drag and drop, you need to install something called VirtualBox Guest Additions (not to be confused with VirtualBox Extension Pack).  The Guest additions get installed into your Guest Operating System (Debian in this case).

But that is another Chapter...


