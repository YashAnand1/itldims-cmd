# Searching Method

## Topics
- Workings of the code
- Command Combinations
- Outputs of Command Combinations

# Workings of the code
- This code utilises a modifed version of  [main.go](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go), where the etcd API url `localhost:8181/servers/` is connected with for displaying all the key-values.
- Data from the API Server is fetched and then the parsing of the data is done before the user inputs their argument/s to process the data from the API Server.
- `itldims` command is used to check connection with the API Server and `itldims get <input 1> <input 2>` subcommand is used to search user arguments from the API Server.
-  The method of placing user arguments into `localhost:8181/servers/<ServerType/ServerIP/Attribtue` is not used and grep like search is run through the displayed content of `localhost:8181/servers`.
- If needed, user can search with a single key-component or value using `itldims get <input 1>`. The 2 inputs entered by the user are then searched for and the key-values not needed are filtered out from the data in `localhost:8181/servers/`.

# Command Combinations
| S. No. | Command Combination               | Output Description                                      | Use-Case |
|-------|-----------------------------------|---------------------------------------------------------|------------|
| 1| `itldims get server`              | Displays attribute values of all Servers              | Helps user see all the running servers with their data. |
| 2| `itldims get <Attribute>`         | Displays all Servers containing a specific Attribute   | Helps User find the RAMs of all servers. |
| 3| `itldims get <Server Type>`       | Displays all Attribute values of a specific Server Type | User can find values of all attributes running on all VMs. |
| 4| `itldims get <Server IP>`         | Displays all Attribute values of a specific Server IP  | User can find values of all attributes running on '10.249.221.22'. |
| 5| `itldims get <Value>` | Displays all Servers containing a specific Attribute value | User can find all the servers that are running 'vahanpgi'. |
| 6| `itldims get <Attribute> <Server Type>` | Displays specific Attribute values of a specific Server Type | User can find CPUs of all VMs. |
| 7| `itldims get <Server Type> <Attribute>` | Displays specific Attribute values of a specific Server Type | User can find CPUs of all VMs. |
| 8| `itldims get <Server Type> <Value>` | Displays all Server Types containing a specific value  | Helps learn if any VM is running 'vahanpgi'. |
| 9| `itldims get <Value> <Server Type>` | Displays all Server Types containing a specific value  | Helps learn if any VM is running 'vahanpgi'. |
| 10| `itldims get <Attribute> <Server IP>`   | Displays specific Attribute values of a specific Server IP   | User can find RAM of '10.249.221.22'. |
| 11| `itldims get <Server IP> <Attribute>`   | Displays specific Attribute values of a specific Server IP   | User can find RAM of '10.249.221.22'. |
| 12| `itldims get <Server IP> <Value>` | Displays all Server IPs containing a specific value  | User can find if any attribute is 'None' on '10.249.221.22'. |
| 13| `itldims get  <Value> <Server IP>` | Displays all Server IPs containing a specific value  | User can find if any attribute is 'None' on '10.249.221.22'. |
| 14| `itldims get <Server IP> <Server Type>` | Displays all Attribute values of a specific Server | Helps find all attribute values for a specific Server. |


## Outputs of Command Combinations
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
- `itldims get <server-Type> <Value>` or `itldims get VM 32GB` is giving the following output:
  ```
  Key: /servers/Physical/10.246.40.152/RAM
  Value: 32GB

  Key: /servers/Physical/10.246.40.139/RAM
  Value: 32GB

  Key: /servers/Physical/10.246.40.142/Internal_Partition
  Value: /:32GB
  ```
- `itldims get <Attribute> <server-IP>` or `itldims get RAM 10.249.221.22` is giving the following output:
  ```
  Key: /servers/VM/10.249.221.22/RAM
  Value: 32GB
  ```
- `itldims get <Attribute> <server-Type>` or `itldims get CPU VM` is giving the following output:
  ```
  Key: /servers/VM/10.249.221.22/CPU
  Value: 8
  ```
- `itldims get <Attribute> <Value>` or `itldims get NFS None` is giving the following output:
  ```
  Key: /servers/VM/10.249.221.21/NFS
  Value: None
  ```
