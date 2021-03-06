## Install VirtualBox Guest Additions for Linux  

We need to install VirtualBox Guest Additions for Linux onto your **Guest OS (ie Debian)** in order to make your guest operating system play more nicely with your host on things like:  
<ul>
  <li>Shared clipboard so you can cut and paste between host and guest
  <li>Shared folder so you can easily move files between host and guest
  <li>Full sized screen so you can size your guest desktop to use as much or as little screen real estate as you like
  <li>Maybe required to allow your guest to use the configured usb ports (not sure -- they might work without this)
</ul>

All of the work in this document takes place in your **Guest/Debian** OS running on the VM.  

This part took me a while to get all the steps correct.  
<ul>
  <li>There is lots of "help" out on the interwebs.  
  <li>Most of it is well intended.  
  <li>Some is dated.  Some has different context, which is not always obvious...  
  <li>Anyway you get the point.
</ul>
Here is what worked for me in a nutshell.  I will show details...
<ol type="i">
  <li>Get the debian 9.3 netinst .iso file that you used to install Debian in the vm <strong>onto your guest filesystem </strong>  
  Remember this was downloaded to your <strong>Host</strong> file system.  We need it on the guest.
  <li>Get the VirtualBox Guest Additions also onto your guest file system.
  <ul><ul><strong>Note</strong> The VirtualBox command bar has a "Devices" tab that contains an entry to "install VirtualBox Guest Additions CD".  I could never get that to work properly.
  </ul></ul>
  <li>Mount the debian iso file to your linux cdrom
  <li>install modules to rebuild the kernel.
  <li>prepare to rebuild the kernel
  <li>Unmount the debian iso file and mount the Guest Additions iso file to cdrom
  <li>Run the Guest Additions install script
</ol>

### Steps

<strong><em>IMPORTANT!!!</em></strong>   When you see references to <code>/user-name/</code> below, do not use that literally unless you happened to have created a linux user called "user-name".  Use the user name you created instead.

<ol>
  <li>Download the Debian netinst ISO file to your linux Downloads folder.
    <ul><ul>
      <li>This is the same one you used on your host Mac to install Debian.  We now need it on the linux file system. 
      <li>This command will download and put it in your /home/user-name/Downloads folder (where "user-name" is your linux user name.)  

```bash
$ wget -P /home/user-name/Downloads "https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-9.3.0-amd64-xfce-CD-1.iso"
```
   </ul></ul>
    
  <li>Download the Virtual Box Guest Additions ISO file to your Downloads folder using a similar wget command  
  
```bash
$ wget -P /home/user-name/Downloads "http://download.virtualbox.org/virtualbox/5.2.2/VBoxGuestAdditions_5.2.2.iso"
```
At this point if you ls your Downloads folder you should see:

```bash
$ ls /home/user-name/Downloads
debian-9.3.0-amd64-xfce-CD-1.iso  VBoxGuestAdditions_5.2.2.iso
```
  <li>Now mount the Debian netinst iso on <code>/media/cdrom</code>  

<code>$ sudo mount -t auto /home/user-name/Downloads/debian-9.3.0-amd64-xfce-CD-1.iso /media/cdrom</code>  

A successful response looks like:  
<samp>mount: /dev/loop0 is write-protected, mounting read-only
</samp>

  <li>Now we have to prepare the system to build kernel modules
  <ol type="a"><ol type="a">
    <li> First make sure everything us up to date 
    <pre><code>
    $ sudo apt-get update  
    $ sudo apt-get upgrade  </code></pre>
    <li>Next install software to build kernel modules, and prepare to build kernel modules
    <pre><code>
    $ sudo apt-get install build-essential module-assistant
    $ sudo m-a prepare</code></pre>
    <li>Next we install the Guest additions
    <pre><code>
    $ sudo sh media/cdrom/VBoxLinuxAdditions.run </code></pre>
  </ol></ol>
</ol>
Success looks like:  
<pre><samp>
Verifying archive integrity... All good.
Uncompressing VirtualBox 5.2.2 Guest Additions for Linux........
VirtualBox Guest Additions installer
Copying additional installer modules ...
Installing additional modules ...
VirtualBox Guest Additions: Building the VirtualBox Guest Additions kernel modules.
VirtualBox Guest Additions: Starting.</samp></pre>

Now Reboot your guest
<code>$ sudo reboot</code>

Once you have rebooted:
<ul>
<li>You should be able to resize your GUI to any part of the screen (slight delay between dragging the corner and the GUI resizing.  
<li>Cut and Paste between host and guest (note, you need to use ctrl-shift-c to copy and ctrl-shift-v to paste on the guest)
<li>Confirm you can see your shared folder (from the host) in <code>/media/sf_"your-shared-folder-name"
<ul>
