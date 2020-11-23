# Disabling Nvidia GPU in Thinkpad P43s running Ubuntu
## Status: Success
## About
Why do I bother making this repository in GitHub when everybody has an internet connection to download and install Ubuntu themselves? Well, there's something that most people failed to do in the post-intall process such as `disabling nvidia gpu` in order to lower the power consumption and save battery life. So I'm here to help you guys. Pardon me with my English and this repository has nothing to do with any order functionality order than disabling nvidia gpu as I have yet to test them in my Thinkpad P43s.
## Please Read
This is not a repository which I will tell you on how to install or configure your Ubuntu. You should be able to configure yourself. This repository is only to help you on how to disable the discrete graphics.

# Specifications
|Category|Component|
|-|-|
|CPU|Intel i7-8565U|
|Memory|16GB DDR4 2666Mhz|
|Display|14" 1920x1080 non-touch|
|SSD|Union Memory 512GB|
|BIOS Version|1.70|
|EC Version|1.22|
## Requirements
- text editor
- internet connection?
- nvidia drivers which can be found [here](https://www.nvidia.com/Download/index.aspx)
# Method of disabling the GPU
## via Ubuntu post-install method based on [Lenovo](https://download.lenovo.com/pccbbs/mobiles_pdf/thinkpad_p43s_p53s_ubuntu_installation_whitepaper_v1.0.pdf)
First, you have to add this line `blacklist nouveau` to `/etc/modprobe.d/blacklist.conf` in order for the Nvidia driver to work. Strange isn't it? Don't worry just follow the steps. Next is to run `update-initramfs -u` and reboot your laptop. Next run these 3 commands in your terminal `sudo apt-get install make`, `sudo apt-get install -y gcc` and `sudo apt-get install -y linux-headers*`. Next, you have to stop x-windows by executing `init 3`. Then login with your username and password. Then locate your nvidia driver that you've downloaded and add this permission to make it executable `sudo chmod +x Nvidia..whatever-the-file-name-is` and execute it with this command `sudo ./Nvidia..whatever-the-file-name-is` follow the installation steps. After the installtion, verify whether the Nvidia driver is working by executing `nvidia-smi` and you shall see the processes etc... Then you shall proceed to the next step.
## via ACPI Calls based on [N0madK](https://forums.lenovo.com/t5/ThinkPad-P-and-W-Series-Mobile/Disable-NVIDIA-P520-on-the-P43s-ACPI-Calls/m-p/4545175)
This step is very simple. Edit your `/etc/default/grub` and add this line `acpi_osi="!Linux-Lenovo-NV-HDMI-Audio"` to your CMDLine such as `GRUB_CMDLINE_LINUX_DEFAULT='quiet splash acpi_osi="!Linux-Lenovo-NV-HDMI-Audio"'` notice how the cmdline has double quote like `GRUB_CMDLINE_LINUX_DEFAULT="quiet splash"`? change it to single quote `'` like so `GRUB_CMDLINE_LINUX_DEFAULT='quiet splash'` then add the following `acpi_osi="!Linux-Lenovo-NV-HDMI-Audio"`. Save the file and proceed with `update-grub` command and restart. You shall proceed to the next step.
## via SSDT Patching based on [Major Hayden](https://major.io/2020/01/24/disable-nvidia-gpu-thinkpad-t490/)
I don't know if this step is necessary.. but you may try.
`TL:DR`
I have simplified the process of SSDT Patching from the original author. What you have to do is to download the file here and run these commands in your terminal.
and then, add this to your GRUB boot entry which is located at `/boot/grub/grub.cfg`. You might want to do the `via ACPI Calls` method first and then go back to this step, else the `update-grub` command will rewrite the grub configuration and you might wanna restart this step. Next
# Supported Device
- P43s
- P53s
- T490 with Nvidia GPU
- T590 with Nvidia GPU
<br>`Not sure about others but might work out the same if you know what you're doing.`
