---
name: Mount & unmount
menu: Unix
---

# Mount && unmount

## List all UUIDs

Linux’s ext2/ext3 filesystem uses UUID to identify partitions.

```shell script
sudo blkid
```

example output

```
/dev/sda1: TYPE="ntfs" UUID="A0F0582EF0580CC2" 
/dev/sda2: UUID="8c2da865-13f4-47a2-9c92-2f31738469e8" SEC_TYPE="ext2" TYPE="ext3" 
/dev/sda3: TYPE="swap" UUID="5641913f-9bcc-4d8a-8bcb-ddfc3159e70f" 
/dev/sda5: UUID="FAB008D6B0089AF1" TYPE="ntfs" 
/dev/sdb1: UUID="32c61b65-f2f8-4041-a5d5-3d5ef4182723" SEC_TYPE="ext2" TYPE="ext3" 
/dev/sdb2: UUID="41c22818-fbad-4da6-8196-c816df0b7aa8" SEC_TYPE="ext2" TYPE="ext3" 
```
## mount 

Open /etc/fstab:

```shell script
sudo vi /etc/fstab
```

Append line as follows:

```
UUID=41c22818-fbad-4da6-8196-c816df0b7aa8  /disk2p2      ext3    defaults,errors=remount-ro 0       1
```

apply the mount
```shell script
sudo mount -a
```

## unmount 

get all the mount point 

```shell script
sudo df --human-readable --print-type
```

make sure the volume is not in used

```shell script
sudo lsof +f -- /mnt/use_your_mount_point
```

unmount it 

```shell script
sudo umount --verbose /mnt/use_your_mount_point
```

