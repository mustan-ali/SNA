* **Extending LVM**
    1. Add a new disk to the VM
    2. Reboot OR rescan the SCSI bus
        * `echo "- - -" > /sys/class/scsi_host/host0/scan`
        * `echo "- - -" > /sys/class/scsi_host/host1/scan`
        * `echo "- - -" > /sys/class/scsi_host/host2/scan`
        * `echo "- - -" > /sys/class/scsi_host/host3/scan`
    3. Use `lsblk` to verify the disk is present
    4. Use `pvcreate` to create a physical volume
        * `pvcreate /dev/sdc`
    5. Use `vgextend` to extend the volume group
        * `vgextend my_vg /dev/sdc`
    6. Use `lvextend` to extend the logical volume
        * `lvextend -L +10G -r /dev/my_vg/my_lv`
    7. Verify the disk is extended
        * `df -hT`

* **Reducing LVM**
    1. Unmount the disk
        * `umount /mnt/my_disk`
    2. Use `lvreduce` to reduce the logical volume
        * `lvreduce -L -5G -r /dev/my_vg/my_lv`
    3. Verify the disk is reduced
        * `df -hT`
    4. Mount the disk
        * `mount /dev/my_vg/my_lv /mnt/my_disk`

* **Removing LVM**
    1. Unmount the disk
        * `umount /mnt/my_disk`
    2. Use `lvremove` to remove the logical volume
        * `lvremove /dev/my_vg/my_lv`
    3. Use `vgremove` to remove the volume group
        * `vgremove my_vg`
    4. Use `pvremove` to remove the physical volume
        * `pvremove /dev/sdb`
    5. Verify the disk is removed
        * `lsblk`