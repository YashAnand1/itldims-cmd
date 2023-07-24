# Possible Commands For Data Retrieval
___
NOTE: keys are in the form of: </*servers*/*server-type*/*server-IP*/*attribute*>
Commands that need to be added: date, time, recently updated.

___

Possible commands for data retrieval in a tabular form are as follows:
| Use cases                                                 | Input                                      | Output                                              |
|-------------------------------------------------------------|------------------------------------------|-----------------------------------------------------|
| 01. Find value of a **specific attribute from a Server IP**  |`itldims get --aip <server IP> <attribute>`|Displays values of an attribute from a server IP  |
| 01. Find value of a **specific attribute from a Server Type**|`itldims get --ast <server Type> <attribute>`|Displays values of an attribute from a server Type |
| 02. Find **list of attributes running from server IP**       |`itldims get --aip <server IP> --all`|Displays all the attributes using Server IP       |
| 02. Find **list of attributes running from server type**     |`itldims get --ast <server type> --all`|Displays all the attributes using Server Type    |
| 03. List **Server IPs containing specific attributes**       |`itldims get --ip <attribute> --only`|Displays Server IPs containing specific attribute |
| 04. Find **Server Types containing specific attributes**     |`itldims get --st <attribute> --only`|Displays Server Type containing specfic attribute |
| 05. Find **Number of stored Server IPs**                     |`itldims get --ip --count`           |Displays the number of Server IPs in the DB |

___

Other possible commands
| Description                                                  | Input                                          | Output                                       |
|--------------------------------------------------------------|------------------------------------------------|----------------------------------------------|
| 01. List values of all attributes from all servers| `itldims get --all`| Values of all attributes of all servers displayed|
| 02. List values of attribute & sort by ascending| `itldims get --aip <server IP> <attribute> --sort-a`| Values of all attributes of all servers displayed|
| 03. List values of attribute & sort by descending             | `itldims get --aip <server IP> <attribute> --sort-d`                    | Values sorted in descending order & displayed                        |
| 04. List values of an attributes between a range              | `itldims get --aip <server IP> <attribute> --range <min num> <max num>` | Values between a range are displayed                                 |
| 05. List the number of times attribute has been changed       | `itldims get --aip <server IP> <attribute> --findrev`                   | Revision number of current value displayed                           |
| 06. List the value of an attribute from an earlier revision   | `itldims get --aip <server IP> <attribute> --rev <revision number>`     | Old version of the value displayed                                   |
| 09. List which server has attribute has specific value        | `itldims get --aip <server IP> <attribute> --find "NONE"`               | Servers containing attribute values as NONE are only displayed       |
| 10. List values of multiple attributes in a server           | `itldims get --aip <server IP> <attribute> <attribute> <attribute>`     | Values of multiple attributes displayed  |
| 11. 'itldims --help' or 'itldims' to provide usage           | `itldims` or `etcdctl --help`                                           | Usage and options related to itldims displayed|

___

Possible flags for facillitating data retrieval
| Description                                     |Input | Output                      |
|--------------------------------------------|----|------------------------------------|
|01. Helps display value of a **attribute from Server IP**|`--aip`|Attributes from Server IP can be found|
|02. Helps display value of a **attribute from Server Type**|`--ast`|Attribute from Server Type can be found|
|03. Helps display **Server IP from attribute**|`--ip`|Server IP from Attribute can be found|
|04. Helps display **Server Type from attribute**|`--st`|Server Type from Attribute can be found|
|05. Helps display **Display all attributes**|`--all` |All attributes can be displayed|
|06. Helps display **Display without values**|`--only`|Only values can be displayed|
|07. Helps display **Display without values**|`--only`|Only values can be displayed|
___
