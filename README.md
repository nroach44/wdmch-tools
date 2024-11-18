# WD My Cloud Home Tools

fwtablectl - Edit the fwtable to add, remove or update firmware and parts.

## Building

```
go build github.com/sgissi/wdmch-tools
```

## Usage
```
Commands:
  show [fwtable-file] - Read from file and show existing entries
  firmware new    [fwtable-file] [type] [file] [sector] [load-address] - Add new firmware
  firmware update [fwtable-file] [type] [file] ....................... - Update entry with new file
  firmware remove [fwtable-file] [type] .............................. - Remove firmware from table
  firmware types  .................................................... - Print available firmware types
  part remove [fwtable-file] [index] - Remove part by index
---
Examples:
  wdmch-tools show /dev/sataa1
  wdmch-tools firmware update fwtable.bin KernelRootFS rootfs.cpio.gz
  wdmch-tools firmware new /dev/sataa1 KernelRootFS rootfs.cpio.gz 67584 0x02200000
  wdmch-tools firmware remove /root/fwtable.bin uBoot
  wdmch-tools part remove /dev/sda1 1
```
