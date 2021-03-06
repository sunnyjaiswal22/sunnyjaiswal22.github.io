---
layout: single
title: 'How to use of Microphone and Camera in Virtual Box'
date: 2022-01-16 20:06:00 +0530
categories: tutorial
---

Linux is great, however there are few times when one has to use Windows only. Follow the following steps to enable use of Microphone and Camera in Windows Guest OS running on Virtual Box on Linux Mint (Ubuntu 20) host OS:

1. Install Virtual Box 6.1 on Linux Mint
2. Make VM for Windows and install Windows 10
3. Install Guest Additions in VM to enable full screen and sharing of clipboard contents
4. Go to VM settings -> Audio and enable audio output and input
5. Install Virtual Box extensions pack using command:

        sudo apt install virtualbox-ext-pack

6. The Virtual Box extension pack can also be downloaded from the URL for your VB version

        https://download.virtualbox.org/virtualbox/

        Direct link for 6.1 version: https://download.virtualbox.org/virtualbox/6.1.0_RC1/Oracle_VM_VirtualBox_Extension_Pack-6.1.0_RC1-134891.vbox-extpack

7. Install the Virutal Box extension pack using the VIrutalBox -> Preferences -> Extension pack -> + -> Choose the downloaded extension pack. It’s OK even if error comes.
8. List available webcams using command:

        vboxmanage list webcams

9. The output should be something like the following:

        Video Input Devices: 1
        .1 "Integrated_Webcam_HD: Integrate"
        /dev/video0


10. Start the Windows VM if not already running
11. Execute the following command to attach the webcam to the VM

        vboxmanage controlvm <vm_name> webcam attach

12. On the Windows VM, go to URL https://webcammictest.com/ to test mic and camera
13. To detach the webcam from guest OS, execute the following command:

        vboxmanage controlvm <vm_name> webcam detach


References:

https://docs.oracle.com/en/virtualization/virtualbox/6.0/admin/webcam-passthrough.html


