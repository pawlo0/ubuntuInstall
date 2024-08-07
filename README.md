# Ubuntu Install

There are various methods to install Ubuntu Linux on a laptop or computer without USB or DVD. One method is by using the program ‘grml-rescueboot‘. Starting with an existing linux system.

### 1. Download the Ubuntu ISO file.

For example, by using:

```
wget https://releases.ubuntu.com/22.04.4/ubuntu-22.04.4-desktop-amd64.iso
```
Or just download using the browser.

### 2. Install grml-rescueboot

Grml-rescueboot is a GRUB rescue tool that can be used to install Ubuntu alongside existing another Linux distribution or in a different disk.

```
sudo apt-get install grml-rescueboot
```

### 3. Setup of grml-rescueboot

After installation of the ‘grml-rescueboot‘ program, there will be an empty directory called ‘grml‘. You can check it out:

```
cd /boot
ls
```

Now we need to copy the previously downloaded Ubuntu ISO file to the empty ‘grml‘ directory.

```
sudo cp ubuntu*.iso /boot/grml/
```

Next, you need to update the GRUB boot loader so that it adds the new Ubuntu to its menu, which in turn will allow us to install it on the hard drive.

```
update-grub
```

## 4. Install Ubuntu From Hard Disk

Once the machine is rebooted, the GRUB boot loader will pop up with an updated menu showing the option to "Grml Rescue System (Ubuntu..."

The biggest advantages of this handy program is that you can download any Linux distribution, add it to the grml boot directory, reboot your machine, and the installation process will start.

If you don’t want to install Ubuntu, you can simply delete the grml directory from your distribution, update the GRUB boot loader, reboot your machine and you are back to your default Linux distribution.
