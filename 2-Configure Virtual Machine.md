# Configure Virtual Machine and install Debian and Raspberry Pi Desktop

In this step we will configure VirtualBox so it is ready to install the operating system we downloaded either from Debian.org or from RaspberryPi.org

This episode will create a Debian 64-bit Virtual Machine with 2GB RAM and 20GB Hard Disk, and will:  
* Configure the VM to enable a shared clipboard between the host and VM systems  
* Configure the VM with a Bridged network adapter and a Local-Host network adapter  
* Configure the VM to access a host USB port  
* Configure the VM to share a folder with the host  

Assumptions:
* You download files to your Mac's "Downloads" folder
* You have admin privs on your Mac
* You have 20GB (ideally more) free space on your Mac's startup disk. The VM will reserve this even when it is not running.

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
This will let you cut and paste between your host and the VM.  
Click on the Settings icon in the VirtualBox setup screen to display the settings dialog.  
Click on the "Advanced" tab of "General" settings.  You will see a screen like this"

![Screen10](https://user-images.githubusercontent.com/26580126/34023026-b5f14f9c-e110-11e7-9fd4-6c5252b0354b.png)

Set the "Shared Clipboard" dropdown to Bidirectional.  
Note:  I have not figured out how to get drag'n'drop to work so I leave it off.

#### Create Network Adapters  
This will configure your VM to use netword resources.  I configure two:  
* a "Bridged" adapter which is (from what I can tell) a pass-through to the hosts network adapter (though I think it gets its own IP)  
* a "Host Only" adapter which (again from what I can tell) is a network that runs between the VM and the host (not sure if it is seen externally)  

While still in VirtualBox "Settings"  click on the "Network" icon.  You will see a screen like this:

![Screen11](https://user-images.githubusercontent.com/26580126/34023046-c7f9ea6e-e110-11e7-9201-8ad2645511de.png)

For "Adapter 1" Change the "attached to" dropdown to "Bridged Adapter"  (refer to above image)  
Then select Adapter 2 and you see a screen like this:

![Screen12](https://user-images.githubusercontent.com/26580126/34023056-d57f1754-e110-11e7-903e-cd0c83342f20.png)  
Click the "Enable Network Adapter" checkbox  (refer to above image)  
Set the "Attached to" pulldown to Host-only Adapter.  The name will auto populate as vboxnet0.  Leave it.

#### Enable your VM to use your host USB ports  
This is useful for example if you have a z-wave usb stick that you want to be able to access from your vm.  Thats how I set it up, but in theory this should work for any USB device  
While sill in VirtualBox "Settings" click on the "Ports" icon  
You will see a screen like this:  
![Screen13](https://user-images.githubusercontent.com/26580126/34023081-edfb4fdc-e110-11e7-9147-edfef4800e16.png)  
Make sure the "Enable USB Controller" check box is checked  
Select the USB controller (Mine is USB 2.0)  
Next click on the icon with the green plus sign on the right side of the dialog box to add a USB device filter.  
Select the device you want.  Mine is a Sigma Designs Z-Stick which is easy to identify.  I have not played with vanilla printer or scanner ports yet.

### Configure a shared directory between VM and host  
In case you want to move files back and forth.

First, setup a directory on your host that will be shared with the VM.  I call mine DebHAShare.

![Screen14](https://user-images.githubusercontent.com/26580126/34024302-5704f09a-e117-11e7-8000-7edad4b4245b.png)

Back in VirualBox Settings, click on the "Shared Folders" icon.  You will see a screen like:

![Screen15](https://user-images.githubusercontent.com/26580126/34024560-d3c94a1c-e118-11e7-96a1-f749d29fd0fa.png)  

Click on the icon with the green plus sign on the right.  You will see this:

![Screen16](https://user-images.githubusercontent.com/26580126/34024572-f0e32f6e-e118-11e7-9964-67d417768f48.png)  

In the "Folder Path" select "other".  This will open a host Finder window where you can select the host shared folder you created.

![Screen17](https://user-images.githubusercontent.com/26580126/34024716-b3dd7006-e119-11e7-9271-2325baf6c86d.png)  

After selecting your host folder the "Shared Folders" dialog box will look like this:
![Screen18](https://user-images.githubusercontent.com/26580126/34024640-4e2b1416-e119-11e7-9e61-321eca4c429a.png)  
Folder Path will show the fully qualified host folder
Folder Name contains the name that you will use as the device name to mount your shared folder in Debian.  Remember it.  
Clicking Auto Mount will mount your shared folder when your Debian system boots in /media/<FolderName>, which in this case will be /media/DebHAShare.  

Click OK and you should see this:  
![Screen19](https://user-images.githubusercontent.com/26580126/34024659-6b28c6d0-e119-11e7-82e5-f192a79858b0.png)  
Click OK again and you should be ready to launch the VM and install Debian.  

## NOTE:  The Optional setups we just did will not all work in Debian until we install the VirtualBox User Additions for linux as part of the OS install

That will be in our next episode.

Go have a beer (assuming you haven't been drinking along with me already!)

