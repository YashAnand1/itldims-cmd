keys are in the form of: </*servers*/*server-type*/*server-IP*/*attribute*>

total connected ips? 
change -s and -t flags.

Possible commands for data retrieval in a tabular form are as follows:
| Use cases                                                 | Input                                      | Output                                               |
|-------------------------------------------------------------|------------------------------------------|-----------------------------------------------------|
| 1. Find value of a **specific attribute from a Server IP**  | `itldims get -s <server IP> <attribute>` |                |
| 1. Find value of a **specific attribute from a Server Type**| `itldims get -t <server IP> <attribute>` |                        |
| 2. Find **list of attributes running on server**            | `itldims get -s <server IP> --all`       |    |
| 2. Find **list of attributes running on a server type**     | `itldims get -t <server type> --all`     |    |
| 3. List **Server IPs containing specific attributes**       | `itldims get -s <attribute> --only`      |      |
| 4. Find **Server Types of attributes**                      | `itldims get -t <attribute> --only`      |    |
| 5. Find **The list of any attributes**                      |                                          |                                                     |

Possible commands for data retrieval in a tabular form are as follows:
| Description                                                  | Input                                          | Output                                       |
|--------------------------------------------------------------|------------------------------------------------|----------------------------------------------|
| 1. List value of a specific attribute from a specific server | `itldims get <server IP> <attribute>`          | Value of attribute displayed                 |
| 2. List values of all attributes from all servers            | `itldims get --all`                            | Values of all attributes of all servers displayed                    |
| 3. List values of all attributes from a server      | `itldims get <server IP>  --all`                 | Values of all attributes of a server displayed                       |
| 4. List values of all atributes from a server without mentioning the value       | `itldims get <server IP> --no-val`               | Values of attribute displayed without server names                   |
| 5. List values of attribute & sort by ascending              | `etcdctl get <key> --sort-a`                    | Values of all attributes of all servers displayed                    |
| 6. List values of attribute & sort by descending             | `etcdctl get <key> --sort-d`                    | Values sorted in descending order & displayed                        |
| 7. List values of an attributes between a range              | `etcdctl get <key> --range <min num> <max num>` | Values between a range are displayed                                 |
| 8. List the number of times a value has been changed         | `etcdctl get <key> --findrev`                   | Revision number of current value displayed                           |
| 9. List the value of an attribute from an earlier revision   | `etcdctl get <key> --rev <revision number>`     | Old version of the value displayed                                   |
| 10. List the recently updated server in ascending order      | `etcdctl get --sort-a --no-val`                 | Recently updated servers are sorted in ascending order and displayed |
| 11. List the recently updated server in descending order     | `etcdctl get --sort-d --no-val`                 | Recently updated servers are sorted in descending order and displayed|
| 12. List which server has NONE                               | `etcdctl get <key> --find NONE`                 | Servers containing attribute values as NONE are only displayed       |
| 13. List servers with particular attributes                  | `etcdctl get <key> --find <value>`              | Servers containing attribute values as the given value are displayed |
| 14. List all servers of a particular server type             | `etcdctl get <key> --find <value>`              | Servers containing attribute values as the given value are displayed |
| 15. List values of multiple attributes in a server           | `etcdctl get <key> <key> <key>`                 | Values of multiple attributes displayed  |
| 16. 'itldims --help' or 'itldims' to provide usage           | `etcdctl` or `etcdctl --help`                   | Usage and options related to itldims displayed|

The same comands which have been mentioned above have been provided below as well in a listed view:
1. list value of a specific attribute from a specific server<br>
input: itldims list <key> <br>
output: value of attribute displayed  

4. list values of all attributes from all servers <br>
input: itldims list --all <br>
output: values of all attributes of a all servers 

5. list values of all attributes from a specific server <br>
input: itldims list <key> --all <br>
output: values of all attributes of a server displayed

6. list values of servers without mentioning the servers (like print_value_only) <br>
input: itldims list <key> --no-val <br>
output: values of attribute displayed without 

7. list values of attribute & sort by ascending <br>
input: itldims list <key> --sort-a <br>
output: values of all attributes of all servers displayed

8. list values of attribute & sort by descending <br>
input: itldims list <key> --sort-d <br>
output: values sorted in descending order & displayed

9. list values of an attributes between a range (RAM between 8GB & 16GB) (show filtered data, only show filtered or searched content) <br>
input: itldims list <key> --range <min num> <max num> <br>
output: values between a range are displayed

10. list the number of times a value of an attribute has been changed (versions) <br>
input: itldims list <key> --findrev <br>
output: revision number of current value displayed

11. list the value of an attribute from an earlier revision <br>
input: itldims list <key> --rev <revision number> <br>
output: old version of the value displayed

12. list the recently updated server in ascending order <br>
input: itldims list --sort-a --no-val <br>
output: recently updated servers are sorted in ascending order and displayed

13. list the recently updated server in descending order <br>
input: itldims list --sort-d --no-val <br>
output: recently updated servers are sorted in descending order and displayed

14. list which server has NONE (NFS & External_Partition can be optional) <br>
input: itldims list <key> --find NONE <br>
output: servers containing attribute values as NONE are only displayed

15. list servers with particular attributes (list servers running vahan) (like command 10) <br>
input: itldims list <key> --find <value> <br>
output: servers containing attribute values as NONE are only displayed

16. list all servers of a particular server type <br>
input: itldims list <key> --find <value> <br>
output: servers containing attribute values as NONE are only displayed

17. list values of multiple attributes in a server <br>
input: itldims list <key> <key> <key> <br>
output: values of multiple attributes displayed

18. 'itldims --help' or 'itldims' to provide usage of itldims <br>
input: `itldims` or `itldims --help` <br> 
output: usage and options related to itldims displayed
