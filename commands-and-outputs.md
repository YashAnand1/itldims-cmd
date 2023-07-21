keys are in the form of: </*servers*/*server-type*/*server-IP*/*attribute*>


<center>Possible commands for data retrieval</center>

| Description                                                 | Input                                    | Output                                         |
|----------------------------------------------------------|------------------------------------------|-------------------------------------------------|
| 1. List value of a specific attribute from a specific server | `itldims list <key>`                      | Value of attribute displayed                   |
| 2. List values of all attributes from all servers         | `itldims list --all`                     | Values of all attributes of all servers displayed   |
| 3. List values of all attributes from a specific server    | `itldims list <key> --all`                | Values of all attributes of a server displayed       |
| 4. List values of servers without mentioning the servers  | `itldims list <key> --no-val`            | Values of attribute displayed without server names   |
| 5. List values of attribute & sort by ascending           | `itldims list <key> --sort-a`            | Values of all attributes of all servers displayed   |
| 6. List values of attribute & sort by descending          | `itldims list <key> --sort-d`            | Values sorted in descending order & displayed         |
| 7. List values of an attributes between a range           | `itldims list <key> --range <min num> <max num>` | Values between a range are displayed                   |
| 8. List the number of times a value has been changed      | `itldims list <key> --findrev`           | Revision number of current value displayed             |
| 9. List the value of an attribute from an earlier revision | `itldims list <key> --rev <revision number>` | Old version of the value displayed                   |
| 10. List the recently updated server in ascending order  | `itldims list --sort-a --no-val`        | Recently updated servers are sorted in ascending order and displayed |
| 11. List the recently updated server in descending order | `itldims list --sort-d --no-val`        | Recently updated servers are sorted in descending order and displayed |
| 12. List which server has NONE                           | `itldims list <key> --find NONE`        | Servers containing attribute values as NONE are only displayed |
| 13. List servers with particular attributes              | `itldims list <key> --find <value>`     | Servers containing attribute values as the given value are displayed |
| 14. List all servers of a particular server type          | `itldims list <key> --find <value>`     | Servers containing attribute values as the given value are displayed |
| 15. List values of multiple attributes in a server        | `itldims list <key> <key> <key>`        | Values of multiple attributes displayed             |
| 16. 'itldims --help' or 'itldims' to provide usage        | `itldims`                               | Usage and options related to itldims displayed    |


1. list value of a specific attribute from a specific server
input: itldims list <key>
output: value of attribute displayed

2. list values of all attributes from all servers
input: itldims list --all
output: values of all attributes of a all servers

3. list values of all attributes from a specific server
input: itldims list <key> --all
output: values of all attributes of a server displayed

4. list values of servers without mentioning the servers (like print_value_only)
input: itldims list <key> --no-val
output: values of attribute displayed without 

5. list values of attribute & sort by ascending
input: itldims list <key> --sort-a
output: values of all attributes of all servers displayed

6. list values of attribute & sort by descending
input: itldims list <key> --sort-d
output: values sorted in descending order & displayed

7. list values of an attributes between a range (RAM between 8GB & 16GB) (show filtered data, only show filtered or searched content)
input: itldims list <key> --range <min num> <max num>
output: values between a range are displayed

8. list the number of times a value of an attribute has been changed (versions)
input: itldims list <key> --findrev
output: revision number of current value displayed

9. list the value of an attribute from an earlier revision
input: itldims list <key> --rev <revision number>
output: old version of the value displayed

10. list the recently updated server in ascending order
input: itldims list --sort-a --no-val
output: recently updated servers are sorted in ascending order and displayed

11. list the recently updated server in descending order
input: itldims list --sort-d --no-val
output: recently updated servers are sorted in descending order and displayed

12. list which server has NONE (NFS & External_Partition can be optional)
input: itldims list <key> --find NONE
output: servers containing attribute values as NONE are only displayed

13. list servers with particular attributes (list servers running vahan) (like command 10)
input: itldims list <key> --find <value>
output: servers containing attribute values as NONE are only displayed

14. list all servers of a particular server type 
input: itldims list <key> --find <value>
output: servers containing attribute values as NONE are only displayed

15. list values of multiple attributes in a server
input: itldims list <key> <key> <key>
output: values of multiple attributes displayed

16. 'itldims --help' or 'itldims' to provide usage of itldims
input: itldims
input: itldims --help 
output: usage and options related to itldims displayed
