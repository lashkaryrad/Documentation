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


### Step Six: Installing Arch Linux.

1. Install The Base of the OS
- ``` pacstrap /mnt base base-devel linux linux-firmware vim ```
![Install_The_structure](pics/installing_archlinux/installing_archlinux-14.png)















