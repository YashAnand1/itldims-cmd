# Modified Grep Like Method

## Overview
- This code utilises a modifed version of the [main.go](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go), where the etcd API url `localhost:8181/servers/` is used to display all the key-values. 
- The key is in the format of `/servers/<server-Type>/<server-IP>/<Attribute>`. The user is allowed to use the `itldims get <input 1> <input 2>`, the user is allowed to search for any possible combinations of key components.
- The 2 inputs entered by the user are then searched for and the unnecessary key-values filtered out from the data in `localhost:8181/servers/`.

## Possible Combinations
`itldims get <input 1> <input 2>` can be used in the following ways:
- `itldims get <server-IP> <server-Type>` will be giving the following output:
  ```
  Key: /servers/VM/10.249.221.22/Netmask
  Value: 255.255.255.128

  Key: /servers/VM/10.249.221.22/API
  Value: CheckpostWebService

  Key: /servers/VM/10.249.221.22/Internal_Disk
  Value: sda:105GB

  Key: /servers/VM/10.249.221.22/PV
  Value: PV Name=/dev/sda3

  Key: /servers/VM/10.249.221.22/data
  Value: {"API":"CheckpostWebService","Application":"checkpost","CPU":"8","Environment":"Production","External_Disk":"sdb:500GB","External_Partition":"u01:322GB","Gateway":"10.249.221.1","Hostname":"SP-CHKP02","Internal_Disk":"sda:105GB","Internal_Partition":"/:20GB\n/var:9GB\n/home:10GB\n/opt:6GB\n/tmp:10GB\n/boot:2GB\n/boot/efi:1GB","LVM":"home\nopt\nroot\nswap\ntmp\nusr\nvar\nvar_log_audit\nlv0","NFS":"None","Netmask":"255.255.255.128","OS":"RHEL 8.7","PV":"PV Name=/dev/sda3\nPV Size=101.00g\nPV Name=/dev/sdb\nPV Size=500.00g","RAM":"32GB","VG":"/dev/mapper/vg0-lv0:500GB"}

  Key: /servers/VM/10.249.221.22/CPU
  Value: 8

  Key: /servers/VM/10.249.221.22/External_Disk
  Value: sdb:500GB

  Key: /servers/VM/10.249.221.22/Gateway
  Value: 10.249.221.1

  Key: /servers/VM/10.249.221.22/LVM
  Value: home

  Key: /servers/VM/10.249.221.22/RAM
  Value: 32GB
  ```
- `itldims get <server-IP> <Attribute>`
- `itldims get <server-IP> <Value>`
- `itldims get <server-Type> <server-IP>`
- `itldims get <server-Type> <Attribute>`
- `itldims get <server-Type> <Value>`
- `itldims get <Attribute> <server-IP>`
- `itldims get <Attribute> <server-Type>`
- `itldims get <Attribute> <Value>`


