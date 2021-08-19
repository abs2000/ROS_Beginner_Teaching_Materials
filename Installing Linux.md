
# Installing Linux
In this guide We will be going through how to install and run Linux Ubuntu 18.04 in 3 different ways. On the surface this may seem like an easy task but there are a lot of issues that you may face along the way. We will highlight some of the issues we encountered and offer solutions, so you dont have to go through the stress that unknown errors bring.

1) via **dual boot** on your PC - this is where you would install the Linux OS, such that it runs the Linux OS as well as your own OS. Switching between the two operating systems happens at reboot
2) via **full installation** on your PC - this is where you would install the Linux OS as the **only** operating system running on your PC. *Warning: this will wipe out all exiting OS, programs, files etc...*
3) via a **virtual machine** running on your PC - here you would download virtual machine software that emulates the Linux environment. You can also download virtual machines that have both Linux and ROS installed. 





## Options 1 & 2 (Installation via dual boot / Full installation)

To use either of these methosd you will need:
1) Your PC
2) A USB stick with a minimum storage of 4 GB (Check on USB or through PC)
3) A bootable software, we personally recommend **Rufus** - this can be found by following this link: https://rufus.ie/en/ and selecting the latest stable version to download

It is advisable to make backup copies of all of your files before proceeding with the download and installation of Linux OS. This could be done by **creating a system restore point** (search google for instructions) or by saving important files onto a **USB**, **Google drive**, or another form of your choosing.

### Preparing the bootable USB Stick
To use the USB as a medium to install linux, the USB must first be made bootable. This process is described below. **Warning: The contents of your USB will be deleted**, so make sure it is empty or you have a backup of it's content.
1) Download Ubuntu 18.04 **desktop image** by clicking the following link:
http://releases.ubuntu.com/18.04/ and selecting the appropriate **desktop version** for your PC. This will download a .iso file onto your PC.
2) Plug in your USB drive and open the Rufus software
3) Make sure that the following is selected for each section:
* Under **Device**, select your **USB drive**.
* Under **Boot selection** select and navigate to the **.iso Ubuntu desktop image** that you downloaded in step 1. 
* Under **Partition scheme** select **MBR**.computer
* Under **Target system** select **BIOS or UEFI**.

[insert an image]

4) Click *start* and wait until the process is complete. You may get a prompt informing you that the disk image is an 'iso hybrid' and a recommendation to install it as a .iso image - **choose the .iso image option**. Rufus may also give you a prompt seeking permission to download further files - **click agree/yes**.

Once completed, you will have a bootable USB drive that you can use to run and install Linux.


### Booting from the USB 
To install the Linux operating system, you will need to have the USB drive plugged in while booting up the PC. You will also need to know which key to press to enter the Boot Menu. Once the computer has begun to start up you will need to click that key like your life depends on it.

These keys are usually either **F1**, **F2**, **F10**, **F12** or **Del**. If you don't know the key you may be able to find out by googling **BIOS key for [*input your computer model*]**. Or just try each of the ones we mentioned at least once

Sometimes, you will find that your PC isn't taking you to the Boot Menu even though you are pressing the correct keys - this could be due to your PC starting up too quickly. 

Here are a few methods to get around this:
1) arguably the easiest way is to click **restart** (on the desktop start menu) while holding the **shift key**. This will take you to a menu entitled **Choose an option** where you will need to press **Troubleshoot** > **Advanced options** > **UEFI Firmware Settings** and proceed to restart. This will automatically reboot the system into the UEFI. This is the first tip described in this video: https://youtu.be/yPLvBo5UCv0 - *thankfully u only need to watch the first minute*
2) Alternatively, if u wish to try frantically pressing a key again, you can stop "fast start-up" by navigating to your **control panel** then selecting **Hardware and Sound** > **Power Options**, then press **"choose what the power buttons do"** (located on the left section of the window), this will take you to the **System Settings**. Finally, click the **Change settings that are currently unavailable**, uncheck the **Turn on fast start-up** and click **save changes**. This should give you an opportunity to press the relevant keys to enter the Boot Menu.
3) If the above two methods have not solved the issue then the PC can be forced to go to the menu described in the first method by turning the PC off completely through holding the **power button** until loss of power. Then turn on and off again once it begins to load until the computer begins to run a **recovery process**. usually after repeating the process 3 times. **Warning: This is a last resort and it could be done a lot easier by using the first method**
4) For those still struggling here is another video to help reach the BIOS: https://youtu.be/IMr5-mEbhTs

Once you've found yourself at the Boot Menu(in the BIOS) you will either need to move the **Boot from USB drive** to the **top of the list**, or select **USB drive**.

If the install for linux doesn't appear and the computer still runs windows, you can temporarily disable the **windows boot manager** in the BIOS, then try again.

### Installing Linux
Once your PC has booted from the USB drive, you will see a purple GNU which you can use to select to boot Ubuntu.

You will be given the option to either run Linux without installation, or to install Linux. Selecting install Linux will take you to the installation guide. You can then pick to install Linux alongside your OS or to erase your disk and install Linux (this will wipe out your current OS along with any files you have such that the only thing is Linux).

**Warning:** We recommend choosing whether to run linux alongside your OS, or to erase the disk, before picking an option, as it will be extremely difficult to change your mind after the process is done. You have been warned!!

### Common Issues 
**Wi-fi not connecting:** you may find that, following installation, Ubuntu doesn't want to connect to the internet. A few solutions to this include:

1) Simply restarting the computer - this could work if your Linux recognises other networks but fails to connect to them.
2) Connecting the PC to your internet via a wired connection and downloading updates - once connected, open the terminal (by hitting Ctrl+Alt+T) and type into the terminal
```
sudo apt update && sudo apt upgrade 
```
* reboot the Linux. 
* You may encounter an error stating: **unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), is another process using it?**. If this error depicted comes up there are a few possible options to try, this link goes through each of them: https://itsfoss.com/could-not-get-lock-error/. Though it is likely you will just need to wait a while for background updates to complete.


## Installation via virtual simulation
If preparing a bootable disk and running it on your PC is too much of a hassle, then you could, alternatively, run via a virtual simulation on your PC. To do this, you will need to download a virtual machine emulator such as **VMware**.

1) Download **Ubuntu 18.04 desktop image** by clicking the following link: http://releases.ubuntu.com/18.04/ and selecting the appropriate desktop version for your PC. This will download a .iso file onto your PC.

2) Download VMware Workstation Player from the following link: https://www.vmware.com/uk/products/workstation-player.html p.s. You want to download the suitable one for your current OS. For example the **windows VM** for a **windows OS**.

3) Run VMware and, once it has loaded, select **Create a New Virtual Machine**.

4) Select **Installer disc image file (iso)** and browse for the Ubuntu desktop image then click **Next**.

5) Follow the installation guide - you will also be asked to specify the disk size and whether you wish for the virtual disk to be stored as a single file or as multiple files. Here you could just follow the recommended or default settings.

### Common Issues
You may find that the virtual disk keeps crashing due to a few issues
* Not enough space on hard drive - remedied by freeing up space on your hard drive
* You have an anti virus software installed that is conflicted with VMware - remedied by changing the anti virus software
* You haven't enabled virtualisation in your Bios settings (common if you have a new computer) - reboot computer and press either the *F1*, *F2*, *F4* *Delete* or the *Esc* keys.
* Too slow - you may find that navigating the basic Linux interface is slow and that program is too slow. You can attempt allocating it more RAM by 




