* **Disk Management**
    * `lsblk` - List block devices
    * `pvs` - Display physical volumes
    * `vgs` - Display volume groups
    * `lvs` - Display logical volumes
    * `pvdisplay` - Display physical volume information
    * `vgdisplay` - Display volume group information
    * `lvdisplay` - Display logical volume information
    

* **Creating LVM**
    1. Add a new disk to the VM
    2. Reboot OR rescan the SCSI bus
        * `echo "- - -" > /sys/class/scsi_host/host0/scan`
        * `echo "- - -" > /sys/class/scsi_host/host1/scan`
        * `echo "- - -" > /sys/class/scsi_host/host2/scan`
        * `echo "- - -" > /sys/class/scsi_host/host3/scan`
    3. Use `lsblk` to verify the disk is present
    4. Use `pvcreate` to create a physical volume
        * `pvcreate /dev/sdb`
    5. Use `vgcreate` to create a volume group
        * `vgcreate my_vg /dev/sdb`
    6. Use `lvcreate` to create a logical volume
        * `lvcreate -L +10G -n my_lv my_vg`
    7. Use `mkfs` to create a filesystem
        * `mkfs.ext4 /dev/my_vg/my_lv`
    8. Create a mount point
        * `mkdir /mnt/my_disk`
    9. Mount the disk
        * `mount /dev/my_vg/my_lv /mnt/my_disk`
    10. Use `df -hT` to verify the disk is mounted
    11. Add the disk to `/etc/fstab`
        * `echo "/dev/my_vg/my_lv /mnt/my_disk ext4 defaults 0 0" >> /etc/fstab`
    12. Verify the mount point
        * `mount -a`