# Formatting the hdd
# List all devices:
sudo fdisk -l | grep '^Disk'
# Make file system:
sudo mkfs.ext4 /dev/sda
# Mount the drive to a dir
sudo mkdir /data
mount /dev/sda /data
#Check the result
df -H
# Modify fstab:
sudo vim /etc/fstab
#device        mountpoint             fstype    options  dump   fsck
/dev/sdb1    /home/yourname/mydata    ext4    defaults    0    1
#Make sure the fstab is correctly configured, otherwise you won't be able to boot up again
sudo mount -fav
