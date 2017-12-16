## Install VirtualBox Guest Additions for Linux  

In order to make your guest operating system play more nicely with your host on things like:  
<ul>
  <li>Shared clipboard so you can cut and paste between host and guest
  <li>Shared folder so you can easily move files between host and guest
  <li>Full sized screen so you can size your guest desktop to use as much or as little screen real estate as you like
  <li>Maybe required to allow your guest to use the configured usb ports (not sure -- they might work without this)
</ul>

Download the Debian netinst ISO file to your linux Downloads folder.
This is the same one you downloaded to your Mac and used to install Debian on the Virtual Box
But we will need to mount on Linux as well and shared folders don't work yet
Open your browser on the guest machine and get the iso file from `https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.3.0-amd64-xfce-CD-1.iso`
(probably fancier ways to do this with the CL but this is what I know)
click the save file which will save it to your /home/username/Downloads folder on linux

Next Download the Linux Guest additions iso

From here `http://download.virtualbox.org/virtualbox/5.2.2/VBoxGuestAdditions_5.2.2.iso`

At this point if you do `ls /home/user-name/Downloads` you should see

Now mount the Debian netinst ISO on /media/cdrom:

`sudo mount -t auto /home/user-name/Downloads/debian-9.3.0-amd64-xfce-CD-1.iso /media/cdrom`

Confirm that it is successful  
`sudo ls /media/cdrom`  
<fill in with copy paste>

### Next part is with props to linuxbabe 

`sudo apt-get update`
`sudo apt-get upgrade`  
Install required packages for building kernel modules (this step seems to need your debian netinst mounted in the cdrom)
`sudo apt-get install build-essential module-assistant`  
Prepare system for building kernel module  
`sudo m-a prepare`  
Should see `Done!`  
Now we need the Guest additions iso.  So unmount /media/cdrom
`sudo umount /media/cdrom/`
Check success by `sudo ls /media/cdrom/`  Should be empty  

Mount the guest addisions ISO   
`sudo mount -t auto /home/user-name/Downloads/VBoxGuestAdditions_5.2.2.iso`  

`sudo sh /media/cdrom/VBoxLinuxAdditions.run`  

Success looks like:  
`VirtualBox Guest Additions: Starting`

Now Reboot your guest


