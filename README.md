# Sagemcom F@ST 5655v2 AC router

## Memory layout

The mtd patitions directly from the NAND chip (128MiB)

```
4 cmdlinepart partitions found on MTD device nand.0

Creating 4 MTD partitions on "nand.0":

0x000000000000-0x000000020000 : "nvram"
0x000000020000-0x0000000c0000 : "bcm"
0x0000000c0000-0x000007b00000 : "ubi"
0x000007b00000-0x000008000000 : "data"

```

The UBI information

```
UBI: physical eraseblock size:   131072 bytes (128 KiB)
UBI: logical eraseblock size:    126976 bytes
UBI: smallest flash I/O unit:    2048
UBI: VID header offset:          2048 (aligned 2048)
UBI: data offset:                4096
UBI: max. sequence number:       8635262
UBI: attached mtd3 to ubi0
UBI: MTD device name:            "ubi"
UBI: MTD device size:            122 MiB
UBI: number of good PEBs:        978
UBI: number of bad PEBs:         0
UBI: number of corrupted PEBs:   0
UBI: max. allowed volumes:       128
UBI: wear-leveling threshold:    4096
UBI: number of internal volumes: 1
UBI: number of user volumes:     8
UBI: available PEBs:             85
UBI: total number of reserved PEBs: 893
UBI: number of PEBs reserved for bad PEB handling: 9
UBI: max/mean erase counter: 9456/8829
UBI: image sequence number:  0
```

The UBI volumes from /dev/mtd3 ("data")

```
Add UBI volume partitions: name=secondaryboot
Add UBI volume partitions: name=uboot
Add UBI volume partitions: name=uboot-rescue
Add UBI volume partitions: name=permanent_param
Add UBI volume partitions: name=rescue
Add UBI volume partitions: name=operational
Add UBI volume partitions: name=filesystem1
Add UBI volume partitions: name=filesystem2
```

The mtd partitions inside UBI volume "operational"

```
Creating 3 MTD partitions on "operational":

0x000000000000-0x00000001f000 : "firm_header"
0x00000001f000-0x0000002aa000 : "kernel"
0x00000028b000-0x0000018f2000 : "rootfs"
```
