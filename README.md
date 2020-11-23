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
## via ACPI Calls based on [N0madK](https://forums.lenovo.com/t5/ThinkPad-P-and-W-Series-Mobile/Disable-NVIDIA-P520-on-the-P43s-ACPI-Calls/m-p/4545175)

## via SSDT Patching based on [Major Hayden](https://major.io/2020/01/24/disable-nvidia-gpu-thinkpad-t490/)
`TL:DR`
I have simplified the process of SSDT Patching. What you have to do is to download the file here and run these commands in your terminal.
and then, add this to your GRUB boot entry. You might want to do the `via ACPI Calls` method first and then go back to this step.
# Supported Device
- P43s
- P53s
- T490 with Nvidia GPU
- T590 with Nvidia GPU
<br>`Not sure about others but might work out the same if you know what you're doing.`
