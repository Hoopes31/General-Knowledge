# Jenkins configurations
Setting workspace configuration settings

This overview is based on a _[video](https://www.youtube.com/watch?v=Cr8XSljgEPI&list=PLhW3qG5bs-L_ZCOA4zNPSoGbnVQ-rp_dG&index=6)_ by Raghav Pal

## Basic Configuration Settings
1. Open Jenkins and navigate to Manage Jenkins -> Configure System
- **Setting parallelization max/min** allows you to set the max number of concurrent jobs.
- **Quiet period** sets a gap between the time a job is requested and the time it is triggered (More or less a patchy fix for failed jobs due to partially loaded files)
- **SCM checkout retry count** indicates how many times Jenkins should retry pulling your repo
- **Restrict project naming** can force roles or users to use certain patterns when creating projects

You can also:

- Set env variables
- Set default url
- Set SSH server
- Set executables 

### Managing Nodes
Setting up distributed builds. Jenkins can set up a master machine tied to additional node machines.

1. Open Jenkins and navigate to Manage Jenkins -> Manage Nodes

#### Creating a new node
Nodes are machines that run your jobs

1. Select 'New Node' from the right side menu
2. Name it
3. Configure the node
- Set the max number of jobs that can run on the selected node
- Label the node
- Usage: Allows you to select how the node is utilized. There are two options
- 1. **Use this node as much as possible** allows the master node to utilize this job to its max potential
- 2. **Only build jobs with label expressions matching this node** allows the user to specify the name of the node. This renders the node useful only if the label is specifically called upon by a job. To see this in action checkout Raghave Pal's video _[here](https://youtu.be/Cr8XSljgEPI?t=7m25s)_

#### Configuring jobs to use specific nodes
Choosing what nodes to run your jobs on

1. Go to you main Jenkins page
2. Right click a job and select 'Configure' from the drop down menu
- Restrict where this project can be run: Allows the user to specify which labled nodes this job can run on

