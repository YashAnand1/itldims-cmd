# Data Retrieval Commands
This repository consits of commands to facilitate data retrieval process from etcd. The basic idea is to retrieve data without mentioning the whole keys but rather only the components of the keys.

## Methods
There are 2 ways of retrieving the data. These are:  
- The modified grep like method. 
- The old method of inputting components of keys. 

## Modified Grep Like Method | [LINK](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/tree/main/Modified-Grep-Like)
- This method utilises the `itldims get <input 1> <input 2>` command. 
- Here the user enters any 2 arguments that are to be searched for. 
- Then, the fetched data which matches the arguments is displayed from the etcd API of `localhost:8181/servers`.

## Inputting Componnents To Keys Method | [LINK](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/tree/main/Old-Keys-Input)
- This method utilises the `itldims get --server <Server IP> <Attribute>` command at the moment. More commands are yet to be created as per [this](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/ListOfCommands.md) command list. 
- In this code, the API is connected with `localhost:8181/servers/<type>/<IP>/<attribute>`.
- User enters the Server IP and the attribute he wishes to learn about and the value is shown.
- It utilises hardcoded "type" in the code for retrieving data of an Attribute from a Server IP in `localhost:8181/servers/<type>/<IP>/<Attribute>`. There should not be any need to hardcode the server type.
