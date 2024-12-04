* **Disk Management**
    * `df` - Display disk usage
        * `-h` - Human readable
        * `-T` - Display the file system type
    * `lsblk` - List block devices
    * `fdisk` - Partition table manipulator
    * `mkfs` - Make a filesystem


* **Creating a Partition, Formatting, and Mounting**
    1. Add a new disk to the VM
    2. Reboot OR rescan the SCSI bus
        * `echo "- - -" > /sys/class/scsi_host/host0/scan`
        * `echo "- - -" > /sys/class/scsi_host/host1/scan`
        * `echo "- - -" > /sys/class/scsi_host/host2/scan`
        * `echo "- - -" > /sys/class/scsi_host/host3/scan`
    3. Use `lsblk` to verify the disk is present
    4. Use `fdisk` to create a new partition
        * `fdisk /dev/sdb`
        * `n` - New partition
        * `p` - Primary partition
        * Partition number (default)
        * First sector (default)
        * `+1G` - Partition size (1GB)
        * `w` - Write changes
    5. Use `lsblk` to verify the partition is present
    6. Use `mkfs` to create a filesystem
        * `mkfs.ext4 /dev/sdb1`
    7. Create a mount point
        * `mkdir /mnt/my_disk`
    8. Mount the disk
        * `mount /dev/sdb1 /mnt/my_disk`
    9. Use `df -hT` to verify the disk is mounted
    10. Add the disk to `/etc/fstab`
        * `echo "/dev/sdb1 /mnt/my_disk ext4 defaults 0 0" >> /etc/fstab`
    11. Verify the mount point
        * `mount -a`