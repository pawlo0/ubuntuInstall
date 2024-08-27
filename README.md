# Ubuntu Install

To remind myself how to install Ubuntu Linux on external drive that can work with either EFI and BIOS.

### 1. Download the Ubuntu ISO file.

For example, by using:

```
wget https://releases.ubuntu.com/22.04.4/ubuntu-22.04.4-desktop-amd64.iso
```
Or just download using the browser. Burn the iso into a USB stick

### 2. Partitioning

Use Gparted to "Create Partition table" of type "msdos" in the disk that you will be installing Ubuntu.

Then either preparing the disk ahead in Gparted or use the "Something else" during Ubuntu instalation. But in order to work, the following partitions need to be created. If using Gparted use flags to flag the swap partition as "swap" and the EFI partition as "boot,esp". Even if using Gparted, when installing Ubuntu, pick "Something else" so you can chose the mount points. From trial and error, the sequence matters:

1. Primary - Ext4 - 1Gb - Mount on /Boot 
2. Primary - Ext4 - (what's left) - Mount on /
3. Primary - swap - 4Gb
4. Primary  - fat32 - EFI - 1Gb

Finish installing Ubuntu. 

### 3. Install some apps
```
sudo apt update && sudo apt install gparted git
```

```
sudo snap install code nextcloud gparted gimp audacity vlc p7zip keepassxc
```

#### 3.1 Librewolf

No need for firefox as I prefer Librewolf
```
sudo snap remove 
```

[https://librewolf.net/installation/debian/](https://librewolf.net/installation/debian/)

#### 3.2 Calibre

[https://calibre-ebook.com/download_linux](https://calibre-ebook.com/download_linux)


#### 3.3 Spotify

```
sudo snap install spotify
```

[https://github.com/SpotX-Official/SpotX-Bash](https://github.com/SpotX-Official/SpotX-Bash)
