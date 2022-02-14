# HPC Accesso

## Lab computers 

- medium compute in th elab computers 
- request access on slack for lab computers 

## URI HPC 

- Download PuTTY and generate ssh2 key pair
- request URI access by e-mailing the public key to hpc@etal.uri.edu with Dr. Brown in cc
- [HPC at URI]()


## HPC Interactive Sessions with Jupyter Notebooks 

Using Notebooks with CCV (Oscar) at Brown
prereq: Get an account on Oscar from CCV

log in to oscar:

```
ssh <username>@ssh3.hac.uri.edu
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

    ```
    scp /path/to/source/file <username>@transfer.ccv.brown.edu:/path/to/destination/file
    ```
