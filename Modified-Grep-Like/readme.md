# Modified Grep Like Method

## Overview
- This code utilises a modifed version of the [main.go](https://github.com/yash-anand-fosteringlinux/Commands-and-Outputs/blob/main/Old-Keys-Input/main.go), where the etcd API url `localhost:8181/servers/` is used to display all the key-values. 
- The key is in the format of `/servers/server-type/server-IP/attribute`. The user is allowed to use the `itldims get <input 1> <input 2>`, the user is allowed to search for any possible combinations of key components.
- The 2 inputs entered by the user are then searched for and the unnecessary key-values filtered out from the data in `localhost:8181/servers/`.
