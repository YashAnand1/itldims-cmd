# Searching Method

## Topics
- Workings of the code
- Command Combinations
- Outputs of Command Combinations
- Requested features

# Workings of the code
- This code utilises a modifed version of  [main.go](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go), where the etcd API url `localhost:8181/servers/` is connected with for displaying all the key-values.
- Data from the API Server is fetched and then the parsing of the data is done before the user inputs their argument/s to process the data from the API Server.
- `itldims` command is used to check connection with the API Server and `itldims get <input 1> <input 2>` subcommand is used to search user arguments from the API Server.
-  The method of placing user arguments into `localhost:8181/servers/<ServerType/ServerIP/Attribtue` is not used and grep like search is run through the displayed content of `localhost:8181/servers`.
- If needed, user can search with a single key-component or value using `itldims get <input 1>`. The input entered by the user are then searched for and the key-values not needed are filtered out from the data in `localhost:8181/servers/`.

# Command Combinations
| S. No. | Command Combination               | Output Description                                      | Use-Case |
|-------|-----------------------------------|---------------------------------------------------------|------------|
| 1| `itldims get servers`              | Displays all the running Servers with their Server IPs | Helps user see all the running servers |
| 2| `itldims get attributes`         | Displays all Attributes   | Helps User find all the attributes |
| 3| `itldims get types`       | Displays all the running Server Types | Helps User find all the server types |
| 4| `itldims get <Server IP>`         | Displays all Attribute values of a specific Server IP  | Helps user find values of a specific server IP|
| 4| `itldims get <server Type>`         | Displays values of a specific server Type  | User can find values of a specific server Type |
| 5| `itldims get <Attribute>`   | Displays values of a specific Attribute   | User can find all the RAMs of all servers |
| 6| `itldims get <Server IP/Type> <attribute>` | Displays all value of attribute from specific server Type/IP | User can find if any attribute is 'None' on '10.249.221.22' |
| 7| `itldims get <Server IP/Type/Attribute> <Value>` | Displays all Server IPs containing a specific value  | User can find if any attribute is 'None' on '10.249.221.22' |

## Outputs of Command Combinations
The possible combinations along with their outputs for the `itldims get` command have been provided below. For any output which is too lengthy, `. . . . .` has been used at the end to signify that the mentioned output gives complete data but is not being shown here completely.

   
**1. `itldims get server`to get the following output:**
```
key=/servers/Physical/10.246.40.139/CPU
8
----------------------------

key=/servers/Physical/10.246.40.139/Environment
Production
----------------------------

key=/servers/Physical/10.246.40.139/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------

key=/servers/Physical/10.246.40.139/VG
/dev/mapper/vg0-lv0:1000GB
----------------------------

key=/servers/VM/10.249.221.21/API
CheckpostWebService
----------------------------

key=/servers/VM/10.249.221.21/Application
checkpost
----------------------------

key=/servers/VM/10.249.221.21/CPU
8
----------------------------

key=/servers/VM/10.249.221.21/External_Partition
u01:322GB
----------------------------

key=/servers/VM/10.249.221.21/Gateway
10.249.221.1
----------------------------

key=/servers/VM/10.249.221.21/RAM
32GB
----------------------------
. . . . .
```

    
**2. `itldims get <Attribute>` or `itldims get RAM` to get the following output:**
```
key=/servers/VM/10.249.221.22/RAM
32GB
----------------------------

key=/servers/VM/10.249.221.21/RAM
32GB
----------------------------

key=/servers/Physical/10.246.40.152/RAM
32GB
----------------------------

key=/servers/Physical/10.246.40.139/RAM
32GB
----------------------------

key=/servers/Physical/10.246.40.142/RAM
32GB
----------------------------
```

**3. `itldims get <Server Type>` or `itldims get VM` to get the following output:**
```
key=/servers/Physical/10.246.40.152/LVM
home
opt
root
swap
tmp
usr
var
var_crash
lv0
----------------------------

key=/servers/VM/10.249.221.22/Hostname
SP-CHKP02
----------------------------

key=/servers/VM/10.249.221.21/API
CheckpostWebService
----------------------------

key=/servers/VM/10.249.221.21/Environment
Production
----------------------------

key=/servers/VM/10.249.221.22/Netmask
255.255.255.128
----------------------------
. . . . .
```

    
**4. `itldims get <Server IP>` or `itldims get 10.249.221.22`  to get the following output:**
```
key=/servers/VM/10.249.221.22/CPU
8
----------------------------

key=/servers/VM/10.249.221.22/Application
checkpost
----------------------------

key=/servers/VM/10.249.221.22/API
CheckpostWebService
----------------------------

key=/servers/VM/10.249.221.22/Internal_Partition
/:20GB
/var:9GB
/home:10GB
/opt:6GB
/tmp:10GB
/boot:2GB
/boot/efi:1GB
----------------------------
. . . . .
```

    
**5. `itldims get <Value>`  or `itldims get vahan`  to get the following output:**
```
key=/servers/Physical/10.246.40.152/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------

key=/servers/Physical/10.246.40.152/Hostname
vahanapp06
----------------------------

key=/servers/Physical/10.246.40.142/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------

key=/servers/Physical/10.246.40.139/Hostname
vahanapp04
----------------------------

key=/servers/Physical/10.246.40.139/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------

key=/servers/Physical/10.246.40.142/Hostname
vahanapp05
----------------------------
```

         
**6. `itldims get <Attribute> <Server Type>` or `itldims get <Server Type> <Attribute>` or `itldims get VM RAM`  to get the following output:**
```
key=/servers/VM/10.249.221.21/RAM
32GB
----------------------------

key=/servers/VM/10.249.221.22/RAM
32GB
----------------------------
```
           
**7. `itldims get <Server Type> <Value>` or `itldims get <Value> <Server Type>` or `itldims get Physical vahan4bkp`  to get the following output:**
```
key=/servers/Physical/10.246.40.139/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------

key=/servers/Physical/10.246.40.152/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------

key=/servers/Physical/10.246.40.142/NFS
NFSPartition name=/vahanapp
NFSPartition Size=vahanapp_2500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahanapp01/vahanapp
NFSPartition name=/nas01
NFSPartition Size=nas01_500
NFSPartition Source=10.246.40.207_/FPG1/VFS1/vahan4bkp/vahan4
----------------------------
```
    
**8. `itldims get <Attribute> <Server IP>`  or `itldims get <Server IP> <Attribute>`  or `itldims get Environment 10.249.221.22`   to get the following output:**
```
key=/servers/VM/10.249.221.22/Environment
Production
----------------------------
```

          
**9. `itldims get <Value> <Server IP>`  or `itldims get <Server IP> <Value>`  or `itldims get 10.249.221.1 10.249.221.22`   to get the following output:**
```
key=/servers/VM/10.249.221.22/Gateway
10.249.221.1
----------------------------
```

         
**10. `itldims get <Server IP> <Server Type>` or `itldims get 10.249.221.22 VM`   to get the following output:**
```
key=/servers/VM/10.249.221.22/Gateway
10.249.221.1
----------------------------

key=/servers/VM/10.249.221.22/Internal_Partition
/:20GB
/var:9GB
/home:10GB
/opt:6GB
/tmp:10GB
/boot:2GB
/boot/efi:1GB
----------------------------

key=/servers/VM/10.249.221.22/Application
checkpost
----------------------------

key=/servers/VM/10.249.221.22/CPU
8
----------------------------

key=/servers/VM/10.249.221.22/Internal_Disk
sda:105GB
----------------------------

key=/servers/VM/10.249.221.22/RAM
32GB
----------------------------
. . . . . 
```

# Requested Features
- Create `--only-key` flag to display only the key
- - **Command:** `itldims get --only servers`
- Create `--exact` flag to search for exact argument/s to filter out information that does not completely match
- - **Command:** `itldims get --exact 8`
