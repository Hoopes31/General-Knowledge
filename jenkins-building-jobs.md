# Jenkins building jobs
Job in creation, job config, running remotely & chaining execution

This overview is based on a _[video](https://www.youtube.com/watch?v=63HEKFh8T2c&index=7&list=PLhW3qG5bs-L_ZCOA4zNPSoGbnVQ-rp_dG)_ by Raghav Pal

## Creating a job
Jobs run code you supply. These can be jobs to test your code, build your code, even deploy your code.

1. From the main Jenkins page select 'New Item'
2. Name, select job type, push ok.

## Understanding the Jenkins job table
The main table columns are as follows

- S: Status of the build (Blue = Success; Red = Failure; Grey = Not run)
- W: Status of the last 5 runs of the build (Sun = Good; Cloudy = Ok; Rainy = Less than ok; Storm = Bad)
- Name: If you select the project name a dropdown will be displayed. (You can trigger builds manually here)
- Last Success: Date
- Last Failure: Date
- Last Duration: Time

## Build triggers
Sets the build order of your jobs

### Triggering jobs remotely
Allows you to trigger builds via URL as long as the Token you create matches

1. Create a token by selecting Trigger builds remotely and filling out the Authentication Token input field
2. Utilize the Jenkins supplied url to trigger the job. **JENKINS_URL/job/JOBNAME/build?token=TOKEN**

### Build periodically
Takes in a **MINUTE HOUR DOM MONTH DOW** configuration and triggers jobs according to the schedule you provide

### Poll SCM
Allows you to set up a timer to check if any of you git repo code has changed. If the repos code has been updated the trigger will start a job.

### Build after other projects are built
Gives you the option to set a build up after another job is completed

## Build
This field tell Jenkins what to build. For example purposes select your shell and have the build output "Test Build Succeeded"

## Post-build Actions
Actions to take once the build is complete. For example:

- Trigger a job
- Send an email

## Chaining jobs
Use the 'Build after other projects are built' build trigger

- Chain multiple jobs off of one trigger by filling out the input field with a comma separated list (BuildTest0, BuildTest1, BuildTest2)
- You can also chain trigger a job by setting a post build action that points to another project