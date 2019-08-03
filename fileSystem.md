# File System

## df command

Prints file system usage. Admits `-h` for _human_.

## blkid command

Shows block device attributes

## /etc/fstab file

Info about devices to mount. Follows the structure:

```
/dev/sda1     	  <folder-to-mount>	ext4	defaults          0       0
UUID=<disk-uuir>  /media/disk01		ext4	defaults          0       0
```

UUID can be found via blkid. `ext4`: disk format.

## mount command

To mount units from fstab file:

```
sudo mount -a
```


