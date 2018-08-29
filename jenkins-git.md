# Jenkins integration with GIT (SCM)
Running jobs, GIT plugin, GIT triggers

This overview is based on a _[video](https://www.youtube.com/watch?v=bGqS0f4Utn4)_ by Raghav Pal

## Adding the git plugin
1. Navigate to Manage Jenkins -> Manage Plugins -> Available tab and search Git Plugin
2. Install the Git Plugin

## Executing a local program within a Jenkins build
1. Create a job (Reference building-jobs-jenkins.md)
2. Set up build information
- Add a build step
- Write script commands in the 'Command' textbox
- When running local host the commands are evaluated on the local path

## Using GIT to execute a program within a Jenkins build
Remote builds trigger when the SCM Poll notices your repos code has changed. To do this you must set up a SCM Poll (timer that tells Jenkins to go see if there is new code on git) and point Jenkins to your git repo.

1. From the name dropdown in the Jenkins table select 'Configure'
2. Under 'Source Code Management' select 'Git' and link your project URL
3. Under 'Build Triggers' select 'Poll SCM' and setup the polling schedule (Takes in a MINUTE HOUR DOM MONTH DOW configuration)

_That's it, jobs should now trigger off of pushed code_