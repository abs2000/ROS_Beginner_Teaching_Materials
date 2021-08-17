
# Installing Linux
There are the a few ways that you can run Linux on your PC. We will be going through how to run Linux Ubuntu 18.04 in 3 different ways:

1) via **dual boot** on your PC - this is where you would install the Linux OS on your PC such that it runs the Linux OS as well as your own OS. Switching between the two operating systems happens at reboot

2) via **full installation** on your PC - this is where you would install the Linux OS that on your PC such that it is the **only** operating system running on your PC. *Warning: this will wipe out all exiting OS, programs, files etc...*

3) via a **virtual machine** running on your PC - this is where you would download virtual machine software that emulates the Linux environment. You can also download virtual machines that have both Linux and ROS installed. 





## Options 1 & 2 (Installation via dual boot / vanilla installation)

In order to do this you will need:
1) Your PC
2) A USB stick with a minimum storage of 4 GB (Check)
3) A bootable software such as Rufus - this can be found by following this link: https://rufus.ie/en/ and selecting the latest stable version to download

It is advisable to make backup copies of all of your files before proceeding with the download and installation of Linux OS.

### Preparing the bootable USB Stick
1) Download Ubuntu 18.04 desktop image by clicking the following link:
http://releases.ubuntu.com/18.04/ and selecting the appropriate desktop version for your PC. This will download a .iso file onto your PC.

2) Plug in your USB drive and open the Rufus software

3) Make sure that the following is selected:
* Under the section of *Device* select the USB drive.
* Under the section of *Boot selection* select and navigate to the .iso Ubuntu desktop image that you downloaded in step 1 
* Under

[insert image 1]

4) Click *start* and wait until the process is complete. You may get a prompt informing you that the disk image is an 'iso hybrid' and a recommendation to install it as a .iso image - choose the .iso image option. Rufus may also get you a prompt seeking permission to download further files - click agree/yes.

Once completed, you will have a bootable USB drive that you can use to run and install Linux.


### Booting from the USB 

To reboot your PC onto a new Linux operating system, you will need to have the USB drive plugged into the PC and also know which keys to press whilst your PC is starting up to enter the Boot Menu.

These keys are usually either F1, F2, F10, F12 or Del - pressing the correct key whilst your PC is starting up will take you into the Boot Menu. 

Sometimes, you will find that your PC isn't taking you to the Boot Menu even though you are pressing the correct keys - this could be due to your PC starting up too quickly. To remedy this, click on the windows start up and navigate to your control panel then select Hardware and Sound>Power Options>System Settings then click the *Change settings that are currently unavailable * and then uncheck the *Turn on fast start-up* and then click on *save changes*. This should mean that you have an opportunity to press the relevant keys to enter the Boot Menu.

If, at this point, you are still unable to access the Boot Menu, attempt pressing the escape key (Esc) immediately after pressing the power key - this tends to pause start up and show you the keys to press to access Boot Menu etc...

Once you've found yourself at the Boot Menu, select Boot from USB drive.


### Installing Linux
Once your PC has booted from the USB drive, you will see a purple GNU which you can use to select to boot Ubuntu.

You will be given the option to either run Linux without installation, or to install Linux. Selecting install Linux will take you to the installation guide. You can then pick to install Linux alongside your OS or to erase your disk and install Linux (this will wipe out your current OS along with any files you have such that the only thing is Linux).

Choose the option that you wish and follow the installation guide.

### Common Issues 
**Wi-fi not connecting:** you may find that, following installation, Ubuntu doesn't want to connect to the internet. A few solutions to this include:

1) 
* Simply restarting the computer - this could work if your Linux recognises other networks but fails to connect to them.
2) 
* Connecting the PC to your internet via a wired connection and downloading updates - once connected, open the terminal (by hitting Ctrl+Alt+T) and type into the terminal
```
sudo apt update && sudo apt upgrade 
```
* reboot the Linux. 
* If you were to encounter an error stating *unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?* then try rebooting the PC.


## Installation via virtual simulation
If preparing a bootable disk and running it on your PC is too much of a hassle, then you could, alternatively, run via a virtual simulation on your PC. To do this, you will need to download a virtual machine emulator such as VMware.

1) Download Ubuntu 18.04 desktop image by clicking the following link:
http://releases.ubuntu.com/18.04/ and selecting the appropriate desktop version for your PC. This will download a .iso file onto your PC.

2) Download VMware Workstation Player from the following link: https://www.vmware.com/uk/products/workstation-player.html

3) Run VMware and, once it has loaded, select *Create a New Virtual Machine*

4) Select *Installer disc image file (iso)* and browse for the Ubuntu desktop image then click *Next*

5) Follow the installation guide - you will also be asked to specify the disk size and whether you wish for the virtual disk to be stored as a single file or as multiple files.

### Common Issues
You may find that the virtual disk keeps crashing due to a few issues
* Not enough space on hard drive - remedied by freeing up space on your hard drive
* You have an anti virus software installed that is conflicted with VMware - remedied by changing the anti virus software
* You haven't enabled virtualisation in your Bios settings (common if you have a new computer) - reboot computer and press either the *F1*, *F2*, *F4* *Delete* or the *Esc* keys.
* Too slow - you may find that navigating the basic Linux interface is slow and that program is too slow. You can attempt allocating it more RAM by 




