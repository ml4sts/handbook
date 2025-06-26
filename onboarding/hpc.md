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
* Start by signing in to your URI SSO within Unity
* After logging in to Unity, go to My PIs to find a list of groups
* Click the ```+``` button and paste `pi_<user>_uri_edu` where user is Dr. Brown's email (before the @) to request to join our group

### Using unity
There are multiple ways to using Unity:
- SSH from your terminal
- Use OnDemand apps that exist on the Unity website (One of which is a VS code framework that comes with a terminal)
- Find that app that makes more sense to the type of work you're doing

  Start at unity cluster, hit dropdown, hit openondemand
  Hit interactive apps, open whatever you want to use
- Partitions
  - uri
  - preempt
- Nodes
- Job duration
- Short qos
- Extra Arguments

### Files on Unity
- You will start in your personal space, this will mostly be for things unity will automatically put there, it will get full quickly
```{important}
Always work in the `/work` directory, your `/home` will get full quickly. 
```

Note for ayman:
Could we write in the path below since this is for people who work with dr brown?

- On Unity you have a small personal space and a larger shared space for the PI team
- To access the shared space do ```cd /work/pi_<nameOfGroupAdmin>```. This is the shared space for the team
- Create your own folder and do your work there ```mkdir <your_name_uri>```
- You can't change anything in anyone else's files without permission but you can view and load them

```{tip}
From your `/home` directory (`cd ~`), use `ln -s /work/pi_brownsarahm_uri_edu/ work` 
to make a link in your `/home` folder called `work` that will be a shortcut to the lab work folder
```

Note for Ayman:
A short desciption of what we can find in each of these files would be useful
-/work/pi_brownsarahm_uri_edu
-/project/pi_brownsarahm_uri_edu

### Llama Enviornment


### Using git/gh on Unity terminal
- git and gh are already installed on Unity
- git is simply accessible with no extra steps necessary
- gh on the other hand exists as a module that needs to be loaded 
``` Modules are packages that exist on the framework that can be loaded individually based on need for your project. To access the list of available modules type "module avail"```
- use `module load gh/2.43.1` (Keep in mind this is currently the latest version) or `module avail` to get the list of available modules with their latest versions that exist

### Unity Helpdesk Slack



![Loading GH Module](https://github.com/user-attachments/assets/8706fdc0-efd1-4010-bb94-a5d7ff6ee2c1)

Checkout [Unity Documentation](https://docs.unity.uri.edu/documentation/) for any thoughts that come to mind. It's a great resource!


