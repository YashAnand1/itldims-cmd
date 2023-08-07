# Filling Keys Method (WORK IN PROGRESS/INCOMPLETE)

## Overview
- This code utilises an [older version](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go) of the [main.go]([https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go](https://github.com/Keen-And-Able/etcd-inventory/blob/sk/main.go)), where the etcd API url `localhost:8181/servers/<server-Type>/<server-IP>/<Attribute>` is used to display all the key-values. 
- The key is in the format of `/servers/<server-Type>/<server-IP>/<Attribute>` and the code is supposed to place the arguments entered by the user through commands like `itldims get --server <Server IP> <Attributes`, in the fore-mentioned key.
- The created key will be then added to `localhost:8181/servers/` and the output will be retrieved as the data.

## Issues
- **Wildcards Not Supported:** Etcdctl by default, [does not allow](https://github.com/etcd-io/etcd/issues/9875#issuecomment-400466889) searching with wildcards. This means that "/servers/*/10.249.221.22/API" will not be giving any value as the key "/servers/VM/10.249.221.22/API" has been broken. However, "--prefix" option can help retrieve values of all attributes from Server Type & IP from "/servers/<Type>/<IP>".
- **Hardcoding A Component:** As stated above, if the key is not complete, etcdctl will not be able to give value. To by-pass this issue, "Server Type = VM" had to be hardcoded for creating `itldims get --server <IP> <Attribute>`. The command works this way but only for servers that are on VMs.

## Possible Combinations
These can be understood in detail through the [list of commands](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/ListOfCommands.md) that are to be created.

## Test Outputs
- Running `itldims get --server 10.249.221.22 RAM` for retrieving value of RAM from Server IP (and the hardcoded VM server type) gives the following output:
  ```
  Value: 32GB
  ```
