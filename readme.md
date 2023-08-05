# Data Retrieval Commands

There are 2 ways of retrieving the data. These are:  
- The modified grep like method. | Link
- The old method of inputting components of keys. | Link

## Modified Grep Like Method  
- This method utilises the `itldims get <input 1> <input 2>` command. 
- Here the user enters any 2 arguments that are to be searched for. 
- Then, the fetched data which matches the arguments is displayed from the etcd API of `localhost:8181/servers`.

## Inputting Componnents To Keys Method  
- This method utilises the `itldims get --server <Server IP> <Attribute>` command at the moment. More commands are yet to be created as per [this](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/ListOfCommands.md) command list. 
- In this code, the API is connected with `localhost:8181/servers/<type>/<IP>/<attribute>`.
- User enters the Server IP and the attribute he wishes to learn about and the value is shown.
- It utilises hardcoded "type" in the code for entering in `localhost:8181/servers/<type>/<IP>/<Attribute>`.
