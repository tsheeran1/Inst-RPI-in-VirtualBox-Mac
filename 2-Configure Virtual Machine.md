# Configure Virtual Machine and install Debian and Raspberry Pi Desktop

In this step we will configure VirtualBox and install the operating system we downloaded from Rasperrypi.org

Same assumptions:  Downloads in ~/username/Downloads folder on iMac and you have "sudo" privs
## Steps

1.  Click on VirtualBox in your Applications Folder (where you installed it).  You should see a screen like this:

![Screen1](https://user-images.githubusercontent.com/26580126/33408691-d8fb3ee8-d545-11e7-8652-a250ed17de8e.png)

2.  Click on the light blue "New" icon. You should see a dialog box like below.  In the "Name" field of the dialog box type "Debian" notice that the other fields autofill:

![Screen2](https://user-images.githubusercontent.com/26580126/33408794-45e7cb52-d546-11e7-844e-4324459d5e4f.png)

3. Click Continue.  You should see a dialog box like below.  For this VM select 2048 MB (2GB) memory (feel free to play with this)

![Screen3](https://user-images.githubusercontent.com/26580126/33408842-8d4669b8-d546-11e7-9096-976a9bb4524b.png)

4. Click Continue.  You should see a dialog box like below.  You DO want a virtual hard disk so click "Create"

![Screen4](https://user-images.githubusercontent.com/26580126/33408888-c7e8d1be-d546-11e7-9dc6-063301e277e8.png)

5. You should see a dialog box like below.  You want VDI (VirtualBox Disk Image) so click "Continue".

![Screen5](https://user-images.githubusercontent.com/26580126/33408923-f28eccf2-d546-11e7-99bc-0710ef7d1891.png)

6. You should see a dialog box like below.  This is tricky.  Dynamic Allocation performs not so great, so select "Fixed Size".  Click 
Continue.

![Screen6](https://user-images.githubusercontent.com/26580126/33408970-18bdabdc-d547-11e7-9238-daff6fabbe24.png)

7. You should see a dialog box like below.  Leave the file location alone ("Debian") and select 20GB disk size (again this is flexible).  Click "Create"

![Screen7](https://user-images.githubusercontent.com/26580126/33409018-51d6b378-d547-11e7-8205-3124820a304f.png)

8. Now you should see a progress box like below as Virtual Box creates your virtual machine.

![Screen8](https://user-images.githubusercontent.com/26580126/33409062-77528460-d547-11e7-88ed-ecfe5a54a94a.png)

And when the smoke clears, you should see a VirtualBox window like this showing your shiny new Debian VM:

![Screen9](https://user-images.githubusercontent.com/26580126/33409179-00bd6cce-d548-11e7-8f31-8fa99f4ef14a.png)

### Optional things you should probably do.  
Your VM will work without this but you will probably want to use this

#### Shared Clipboard
This will let you cut and paste between your host and the VM





### Do you feel accomplished?
Yeah, well don't get too excited yet.  All you have is an empty VM.  In our next chapters we will download the operating system from RaspberryPi.org and then actually install the operating system.

Go have a beer.

