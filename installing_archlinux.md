# Installing Arch Linux on vmware-fusion

### 1. Step One: Install the ISO file.
1. GoTo <a href="https://archlinux.org/">Archinux</a> website and download the ISO
2. check the Validation with sha256

### 2. Step Two: Setup the VM in VmWare.
1. GoTo New and create new Virtual Machine.
![Install_The_VM](/pics/installing_archlinux/installing_archlinux-1.png)

1. Click the <B><i>Install from disc or image</i></B>
2. Choose or drag your disc image.
![Select_The_Disc_image](/pics/installing_archlinux/installing_archlinux-2.png)

1. Click continue.
2. Choose <B><i>Other Linux 5.x kernel 64-bit</i></B>
![Select_kernel_Version](/pics/installing_archlinux/installing_archlinux-3.png)

1. Click continue.
2. Select <B><i>Legacy BIOS</i></B>
![Choose_FirmWare_Type](/pics/installing_archlinux/installing_archlinux-4.png)

1. Click continue.
2. And then Hit Finish.
![Finish_the_Configuration](/pics/installing_archlinux/installing_archlinux-5.png)

### 3. Boot In To the Vm.
1. Click <B><i>Arch Linux Install Medium (x86_64, BIOS)</i></B>
![Boot_Menu](/pics/installing_archlinux/installing_archlinux-6.png)

### 4. Step Three: Setup The Time
- ``` timedatectl set-ntp true ``` 

![Setup_Time](pics/installing_archlinux/installing_archlinux-7.png)

### 5. Step Five: Partitioning.
1. See the what Disk do you have ``` fdisk -l ``` 
![Disks](/pics/installing_archlinux/installing_archlinux-8.png)

2. Partition the <B><i>``` /dev/sda ```</i></B>
![Partition_sda](pics/installing_archlinux/installing_archlinux-9.png)

3. Write ``` n ``` for new patition
![Create_New_Partition](pics/installing_archlinux/installing_archlinux-10.png)

4. Write ``` w ``` for Write & quit
![Write_Changes](pics/installing_archlinux/installing_archlinux-11.png)

5. Format the Partiition: ``` mkfs.ext4 /dev/sda1 ```
![Format_partition](pics/installing_archlinux/installing_archlinux-12.png)

6. Mount The Partition: ``` mount /dev/sda1 /mnt ```
![Mount_Partition](pics/installing_archlinux/installing_archlinux-13.png)


### 6. Step Six: Installing Arch Linux.

1. Install The Base of the OS
- ``` pacstrap /mnt base base-devel linux linux-firmware vim ```
![Install_The_structure](pics/installing_archlinux/installing_archlinux-14.png)

### 7. Step Seven: FSTab Configuration.

- ``` genfstab -U /mnt >> /mnt/etc/fstab ```
![Generate_FSTab](pics/installing_archlinux/installing_archlinux-15.png)

### 8. Step Eight: Chroot into our arch linux.

- ``` arch-chroot /mnt /bin/bash ```

### 9. Step Nine: Install NetworkManager and Grub.

- ``` pacman -S networkmanager grub ```
- enable NetworkManager in systemd ``` systemctl  ```
![Enable_NetwokManager_in_systemd](pics/installing_archlinux/installing_archlinux-17.png)
> Make sure you've spell it correctlly and Notis the capitalize. 

### 10. Step Ten: Configure The Grub.

1. install Grub on <B><i>``` /dev/sda ```</i></B>
    - ``` grub-install /dev/sda ```
    ![Grub_install](pics/installing_archlinux/installing_archlinux-18.png)

2. Generate Configuration File.
    - ``` gurb-mkconfig -o /boot/grub/grub.cfg ```
    ![Grub_MkConfiig](pics/installing_archlinux/installing_archlinux-19.png)


### 11. Step Eleven: Set a PassWord For root User.
- ``` passwd ```

### 12. Step Twelve: Generate Locale.

- ``` vim /etc/locale.gen ```
- UnCommnet The en_US lines
    ![uncommnet_locales](pics/installing_archlinux/installing_archlinux-20.png)

- Then Generate Locale: ``` locale-gen ```
    ![Generate_Locale](pics/installing_archlinux/installing_archlinux-21.png)

- Define Language in <B><i>``` locale.conf ```</i></B>
    - ``` vim /etc/locale.conf ```
        - ``` LANG=en-US.UTF-8 ```
        ![Define_Language](pics/installing_archlinux/installing_archlinux-22.png)

- Setup The HostName: 
    - ``` vim /etc/hostname ```


- Link TimeZone: ``` ln -sf /usr/share/zoneinfo/Asia/Tehram /etc/localtime ```
    ![Link_TimeZone](pics/installing_archlinux/installing_archlinux-23.png)

### 13. Step Thirteen: Done The Installation.

> Exit out the chroot Environment:

1. ``` exit ``` in chroot
2. ``` umoumt -R /mnt ```
![Done_The_Installation](pics/installing_archlinux/installing_archlinux-24.png)


3. Reboot The system: <B><i>``` rebbot ```</i></B>

### 💥 Boom 
![Boom](pics/installing_archlinux/installing_archlinux-25.png)









