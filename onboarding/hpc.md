# HPC Access

## Lab computers 

- medium compute in the lab computers 
- request access on slack for lab computers
- there is a default password there

## URI HPC 


- request URI access by e-mailing with Dr. Brown in cc
- [HPC at URI]()


## Unity HPC

### Requesting access to [Unity Cluster](https://unity.uri.edu/) .
* Start by signing in to your URI account within Unity
* Ask your professor for the teams pi ID (Usually looks something like pi_<name>_uri_edu
* After logging in to Unity, go to My PIs to find a list of groups
* Click the ```+``` button and paste the pi ID you got to request access

### Using Unity
There are multiple ways to using Unity:
- SSH from your terminal
- Use OnDemand apps that exist on the Unity website (One of which is a VS code framework that comes with a terminal)
- Find that app that makes more sense to the type of work you're doing

### Files on Unity
- On Unity you have a small personal space and a larger shared space for the PI team
- To access the shared space do ```cd /work/pi_<nameOfGroupAdmin>```. This is the shared space for the team
- Create your own folder and do you work there ```mkdir <folderName>```

### Using git/gh on Unity terminal
- git and gh are already installed on Unity
- git is simply accessible with no extra steps necessary
- gh on the other hand exists as a module that needs to be loaded 
``` Modules are packages that exist on the framework that can be loaded individually based on need for your project. To access the list of available modules type "module avail"```
- type ```module load gh/2.43.1`` (Keep in mind this is currently the latest version. Type ```module avail``` to get the list of available modules with their latest versions that exist

![Loading GH Module](https://github.com/user-attachments/assets/8706fdc0-efd1-4010-bb94-a5d7ff6ee2c1)

Checkout [Unity Documentation](https://docs.unity.uri.edu/documentation/) for any thoughts that come to mind. It's a great resource!


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

    ```
    scp /path/to/source/file <username>@transfer.ccv.brown.edu:/path/to/destination/file
    ```



## Unity

- https://unity.uri.edu/panel/account.php
- Either use Jupyter notebook for a more user interface-based experience. If preferred consol/CMD, add the SSH key to the local computer by following the following steps.
- Generate the SSH key from the account. The key should begin with ssh-rsa… … …. 
- Use the key to setup a configuration file to the local system. To do this, save the ssh key as a .key file. Notepad++ can be used for this. 
- Save the .key file to a folder. Such as: C:\Users\pujag\.ssh\unity-privkey.key.
- Then generate a configuration file to connect to Unity. 


## The configuration file should be like the following:

- “Host unity
- HostName unity.rc.umass.edu
- User puja_ghosh_uri_edu
- IdentityFile C:\Users\pujag\.ssh\unity-privkey.key”

- Save the file to C:\Users\pujag\.ssh\ as config file. This file should have no file extension. The file name should be only config. 

- Now Unity can be launched by opening CMD and running the code “ssh unity”

- The details are documented here https://docs.unity.uri.edu/connecting/ssh.html


  ## Add Git to Unity with SSH:

- To pull or clone any Git repository, Git does not use password anymore. It uses SSH key. To generate the key, go to account>settings>SSH..>generate a new key. 
- Save the key to a secure location. This key replaces the password. Whenever the console asks for password, use this key instead.

## To add Git account to the system, run the following command in the console:

- ssh-keygen -t ed25519 -C "your_email@example.com"
- Note: If you are using a legacy system that doesn't support the Ed25519 algorithm, use:
ssh-keygen -t rsa -b 4096 -C “your_email@example.com”
- when the command asks for a file name click enter to set it to default. The command should look like this “> Enter a file in which to save the key (/c/Users/YOU/.ssh/id_ALGORITHM):[Press enter]”
- This will generate a .ssh folder in the home directory. This cannot be directly seen in the file browser as it is a hidden folder. To show hidden folders turn on show dot folders in https://ood.unity.rc.umass.edu/pun/sys/dashboard/files/fs//home/<user_name>
- The folder now contains two key files privet and public. The id_rsa is the privet key and id_rsa.pub is the public key. 
- Open the public key file, copy the key (the key starts with ssh-rsa) and add it to your git profile. Profile>settings>SSH…>add new key.
- This will add the remote server to your account.
- Now run “ssh -T git@github.com” to check if your username shows up in the console. This will confirm that the account has been added. 


