## Create Arch ISO or Use Image

Download ArchISO from <https://archlinux.org/download/> and put on a USB drive with [Etcher](https://www.balena.io/etcher/), [Ventoy](https://www.ventoy.net/en/index.html), or [Rufus](https://rufus.ie/en/)

## Boot Arch ISO

From initial Prompt type the following commands:

```
pacman -Sy git
git clone https://github.com/frickenhek/ArchJordan
cd ArchJordan
./archjordan.sh
```
### Do the following if you want my setup

```
Choose yay
Choose ext4
Choose minimal
choose based-kde
```
You will have to debloat a lot of the KDE stuff, but only if you want to, I think all the KDE bloat amounts to 100 maybe 200 MB, so it's not really necessary

### System Description
This is completely automated arch install. It includes prompts to select your desired desktop environment and window manager. The KDE desktop environment on arch includes all the packages I use on a daily basis, as well as some customizations.

## Troubleshooting

__[Arch Linux Wiki Installation Guide](https://wiki.archlinux.org/title/Installation_guide)__

The main script will generate .log files for every script that is run as part of the installation process. These log files contain the terminal output so you can review any warnings or errors that occurred during installation and aid in troubleshooting. 
### No Wifi

You can check if the WiFi is blocked by running `rfkill list`.
If it says **Soft blocked: yes**, then run `rfkill unblock wifi`

After unblocking the WiFi, you can connect to it. Go through these 5 steps:

#1: Run `iwctl`

#2: Run `device list`, and find your device name.

#3: Run `station [device name] scan`

#4: Run `station [device name] get-networks`

#5: Find your network, and run `station [device name] connect [network name]`, enter your password and run `exit`. You can test if you have internet connection by running `ping google.com`, and then Press Ctrl and C to stop the ping test.

