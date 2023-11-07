# HPC Access

## Lab computers 

- medium compute in the lab computers 
- request access on slack for lab computers
- there is a default password there

## URI HPC 


- request URI access by e-mailing with Dr. Brown in cc
- [HPC at URI]()


## Unity



## HPC Interactive Sessions with Jupyter Notebooks 

Using Notebooks with CCV (Oscar) at Brown
prereq: Get an account on Oscar from CCV

log in to oscar:

```
ssh <username>@ssh.ccv.brown.edu
```
To use a notebook on oscar, you will need an interactive session. Get one with the following: see the above documentation

```
interact -t 01:00:00 -m 100g
```
that gives a time (-t)limit of 1 hour and (100Gb) of ram on one (default number) node

1. load python 3.6. You can also add this to your auto load as described in the help on software

    ```
    module load python/3.6.6
    ```
1. (optional, recommended, cd to project folder) launch a notebook to be used remotely

    ```
    jupyter notebook --no-browser --ip=$(hostname -i) --port=8888
    ```
    the notebook will launch and the response will include the ip address and the token.
    ```
    http://172.20.204.32:8888/?token=a40dd28fc49f415b9e2f5c867c653ee9d458bb8c74432575
    http://<ip-address>:<remote_port>/?token=<token>
    ```
1. in a new terminal window locally, ssh again to map the notebook to a local port

    ```
    ssh -N -L 8000:172.20.204.32:8888 <user>@ssh6.ccv.brown.edu
    ```
    enter your password and nothing will happen, but it will be working.
1. point browser to localhost:8000 and enter the token to access the notebook server
1. moving files to work locally if neeeded with:


#Log into Unity account and run commands:

-https://unity.uri.edu/panel/account.php
-Either use Jupyter notebook for a more user interface-based experience. If preferred consol/CMD, add the SSH key to the local computer by following the following steps.
-Generate the SSH key from the account. The key should begin with ssh-rsa… … …. 
-Use the key to setup a configuration file to the local system. To do this, save the ssh key as a .key file. Notepad++ can be used for this. 
-Save the .key file to a folder. Such as: C:\Users\pujag\.ssh\unity-privkey.key.
-Then generate a configuration file to connect to Unity. 

##The configuration file should be like the 
following:

-“Host unity
-HostName unity.rc.umass.edu
-User puja_ghosh_uri_edu
-IdentityFile C:\Users\pujag\.ssh\unity-privkey.key”

-Save the file to C:\Users\pujag\.ssh\ as config file. This file should have no file extension. The file name should be only config. 

-Now Unity can be launched by opening CMD and running the code “ssh unity”

-The details are documented here https://docs.unity.uri.edu/connecting/ssh.html


    ```
    scp /path/to/source/file <username>@transfer.ccv.brown.edu:/path/to/destination/file
    ```