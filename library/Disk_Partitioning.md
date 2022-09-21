# Disk Partitioning
 
### fdisk
For manipulating disk partition table. Can divide block devices into logical disks using GPT, MBR, Sun, SQI and BSD tables.

Syntax: `fdisk [options] [device]`

- View all disk partitions
`fdisk -l`

- View a partition on a specific disk
`fdisk -l [partition]`

- Use fdisk utilities(m for help)
`fdisk [partition]`



### blkid
Used for locating block devices and report on their attributes. It can determine the type of content (e.g. filesystem, swap) a block device holds, and also attributes (tokens, NAME=value pairs) from the content metadata (e.g., LABEL or UUID fields).

Syntax: `blkid [options] [object]`

- List block devices 
`blkid`

- List block devices and mount point
`blkid -o list`

- View I/O limits
`blkid -i [partition]`

- Display additional information
`blkid -ip [partition]`

- Look up for parameters
`blkid -l -t [type=value]`


### lsblk
Presents block device information in a tree format.

Syntax: `lsblk [options] [device]`

- List devices, including empty
`lsblk -a`

- List and print information about owner, group and mode
`lsblk -m`

### dd
For converting and copying files(if: input file; of: output file)

Syntax: `dd [operand]...`

- Create an empty file
`dd if=/dev/zero of=[filename] bs=[bytes_size] count=[amount of bs blocks]`

- Conversion character format
`dd if=file.ebcdic of=file.ascii conv=ascii`

- Copy a full disk
`dd if=/dev/sda of=/dev/sdb`

### sgdisk
Command-line GUID partition table (GPT) manipulator for Linux and Unix

- Print the partition table
`sgdisk -p [disk]`

- Delete the N partition
`sgdisk -d [N] [disk]`

- Create a new partition number N, starting at XMiB and ending in YMiB
`sgdisk -n N:XMiB:YMiB [disk]`

### gdisk
Interactive menu driven GUID partition table manipulator

### losetup
Set up and control loop devices with regular files or block devices, to detach loop devices, and to query the status of a loop device. If only the loopdev argument is given, the status of the corresponding loop device is shown.

### parted
A partition manipulation program including multiple partition table formats. Useful for creating space for new operating systems, reorganising disk usage, and copying data to new hard disks.

### df
Report the amount of disk space available on the filesystem containing each file name argument