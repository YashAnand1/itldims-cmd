keys are in the form of: </*servers*/*server-type*/*server-IP*/*attribute*>

total connected ips? 
change -s and -t flags.

Possible commands for data retrieval in a tabular form are as follows:
| Use cases                                                 | Input                                      | Output                                              |
|-------------------------------------------------------------|------------------------------------------|-----------------------------------------------------|
| 1. Find value of a **specific attribute from a Server IP**  |`itldims get --aip <server IP> <attribute>`|Displays values of an attribute from a server IP  |
| 1. Find value of a **specific attribute from a Server Type**|`itldims get --ast <server Type> <attribute>`|Displays values of an attribute from a server Type |
| 2. Find **list of attributes running from server IP**       |`itldims get --aip <server IP> --all`|Displays all the attributes using Server IP       |
| 2. Find **list of attributes running from server type**     |`itldims get --ast <server type> --all`|Displays all the attributes using Server Type    |
| 3. List **Server IPs containing specific attributes**       |`itldims get --ip <attribute> --only`|Displays Server IPs containing specific attribute |
| 4. Find **Server Types containing specific attributes**     |`itldims get --st <attribute> --only`|Displays Server Type containing specfic attribute |
| 5. Find **Number of stored Server IPs**                     |`itldims get --ip --count`           |Displays the number of Server IPs in the DB |

Other possible commands
| Description                                                  | Input                                          | Output                                       |
|--------------------------------------------------------------|------------------------------------------------|----------------------------------------------|
| 1. List values of all attributes from all servers            | `itldims get --all`                            | Values of all attributes of all servers displayed                    |
| 2. List values of attribute & sort by ascending              | `itldims get <key> --sort-a`                    | Values of all attributes of all servers displayed                    |
| 3. List values of attribute & sort by descending             | `itldims get <key> --sort-d`                    | Values sorted in descending order & displayed                        |
| 4. List values of an attributes between a range              | `itldims get <key> --range <min num> <max num>` | Values between a range are displayed                                 |
| 5. List the number of times a value has been changed         | `itldims get <key> --findrev`                   | Revision number of current value displayed                           |
| 6. List the value of an attribute from an earlier revision   | `itldims get <key> --rev <revision number>`     | Old version of the value displayed                                   |
| 7. List the recently updated server in ascending order      | `itldims get --sort-a --no-val`                 | Recently updated servers are sorted in ascending order and displayed |
| 8. List the recently updated server in descending order     | `itldims get --sort-d --no-val`                 | Recently updated servers are sorted in descending order and displayed|
| 9. List which server has NONE                               | `itldims get <key> --find NONE`                 | Servers containing attribute values as NONE are only displayed       |
| 10. List values of multiple attributes in a server           | `itldims get <key> <key> <key>`                 | Values of multiple attributes displayed  |
| 11. 'itldims --help' or 'itldims' to provide usage           | `itldims` or `etcdctl --help`                   | Usage and options related to itldims displayed|

Possible flags for facillitating data retrieval
| Description                                     |Input | Output                      |
|--------------------------------------------|----|------------------------------------|
|Helps display value of a **attribute from Server IP**|`--aip`|Attributes from Server IP can be found|
|Helps display value of a **attribute from Server Type**|`--ast`|Attribute from Server Type can be found|
|Helps display **Server IP from attribute**|`--ip`|Server IP from Attribute can be found|
|Helps display **Server Type from attribute**|`--st`|Server Type from Attribute can be found|
|Helps display **Display all attributes**|`--all` |All attributes can be displayed|
|Helps display **Display without values**|`--only`|Only values can be displayed|
