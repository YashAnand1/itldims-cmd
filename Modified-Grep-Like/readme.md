# Modified Grep Like Method

## Overview
- This code utilises a modifed version of the [main.go](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go), where the etcd API url `localhost:8181/servers/` is used to display all the key-values. 
- The key is in the format of `/servers/<server-Type>/<server-IP>/<Attribute>`. The user is allowed to use the `itldims get <input 1> <input 2>`, the user is allowed to search for any possible combinations of key components.
- The 2 inputs entered by the user are then searched for and the unnecessary key-values filtered out from the data in `localhost:8181/servers/`.

## Possible Combinations
`itldims get <input 1> <input 2>` can be used in the following ways:
- `itldims get <server-IP> <server-Type>` or `itldims get 10.249.221.22 VM ` is giving the following output:
  ```
  Key: /servers/VM/10.249.221.22/Gateway
  Value: 10.249.221.1

  Key: /servers/VM/10.249.221.22/LVM
  Value: home

  Key: /servers/VM/10.249.221.22/CPU
  Value: 8

  Key: /servers/VM/10.249.221.22/API
  Value: CheckpostWebService

  Key: /servers/VM/10.249.221.22/PV
  Value: PV Name=/dev/sda3

  Key: /servers/VM/10.249.221.22/External_Disk
  Value: sdb:500GB

  Key: /servers/VM/10.249.221.22/Internal_Disk
  Value: sda:105GB

  Key: /servers/VM/10.249.221.22/RAM
  Value: 32GB

  Key: /servers/VM/10.249.221.22/Netmask
  Value: 255.255.255.128
  ```

- `itldims get <server-IP> <Value>`or `itldims get 10.246.40.142 vahan` is giving the following output:
  ```
  Key: /servers/Physical/10.246.40.142/Application
  Value: vahantaxws

  Key: /servers/Physical/10.246.40.142/Hostname
  Value: vahanapp05
  ```

- `itldims get <server-IP> <Attribute>` or `itldims get 10.249.221.22 RAM` is giving the following output:
  ```
  Key: /servers/VM/10.249.221.22/RAM
  Value: 32GB
  ```
- `itldims get <server-Type> <server-IP>`
  ```
  Key: /servers/Physical/10.246.40.142/VG
  Value: /dev/mapper/vg0-lv0:1000GB

  Key: /servers/Physical/10.246.40.142/OS
  Value: RHEL 7.9

  Key: /servers/Physical/10.246.40.142/External_Partition
  Value: u01:1000GB

  Key: /servers/Physical/10.246.40.142/External_Disk
  Value: sdc:500GB

  Key: /servers/Physical/10.246.40.142/Application
  Value: vahantaxws

  Key: /servers/Physical/10.246.40.142/Internal_Partition
  Value: /:32GB

  Key: /servers/Physical/10.246.40.142/LVM
  Value: home

  Key: /servers/Physical/10.246.40.142/CPU
  Value: 8

  Key: /servers/Physical/10.246.40.142/Hostname
  Value: vahanapp05
  ```
- `itldims get <server-Type> <Attribute>` or `itldims get VM 10.249.221.22` is giving the following output:
  ```
  Key: /servers/VM/10.249.221.22/LVM
  Value: home

  Key: /servers/Physical/10.246.40.142/LVM
  Value: home
  ```
- `itldims get <server-Type> <Value>`
- `itldims get <Attribute> <server-IP>`
- `itldims get <Attribute> <server-Type>`
- `itldims get <Attribute> <Value>`


