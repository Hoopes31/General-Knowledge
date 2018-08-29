# Jenkins getting started tutorial
Downloading Jenkins, interfacing & basic user management

This overview is based on a _[video](https://www.youtube.com/watch?v=89yWXXIOisk&index=1&list=PLhW3qG5bs-L_ZCOA4zNPSoGbnVQ-rp_dG)_ by Raghav Pal

## Downloading Jenkins
1. Download _[here](https://jenkins.io/download/)_
2. Run the executable and Jenkins will run and give you an initial admin password
- If you miss the password, it is also stored in _.jenkins/secrets/initialAdminPassword_ file
3. Save the password for future use -or- create a new user in the next step

## Interfacing with Jenkins
1. Run Jenkins by typing `java -jar jenkins.war` in your cli
- To run an alternate location run ``java -jar jenkins.war -httpPort={YOUR_PORT}`
2. Open your browser and head to http://localhost:8080/ (port may vary)

## Changing the Jenkins home directory
This isn't necessary, but can be useful in the future

1. Create a new folder
2. Copy all data from the .Jenkins directory (location listed at the top of http://localhost:8080/configure)
3. Paste all the data into the new folder
4. Set the JENKINS_HOME env variable to the new directory location (Windows)
    - Navigate to your environment variables
    - Set JENKINS_HOME's variable to your new folder path
5. Set the JENKINS_HOME env varaible `export JENKINS_HOME={NEW_FOLDER_PATH}` (Mac)
6. Restart Jenkins (http://localhost:8080/restart)

_To view all system variables go to /systemInfo_

## Managing users and roles
Giving access and creating users

### Creating a user
1. Open Jenkins and Manage Jenkins -> Manage Users -> Create User
2. Enter user info

### Role management
1. Download management plugin [Jenkins Role Strategy Plugin](https://wiki.jenkins.io/display/JENKINS/Role+Strategy+Plugin)
2. Move the downloaded file into {Jenkins Home Directory}/Plugins (You also have the option to add a plugin via the dashboard's Plugin Manager)
3. Go to Manage Jenkins -> Configure Global Security: under Authorization select "Role-Based-Strategy", Apply & save.

#### Create Roles
1. Navigate to Manage Jenkins -> Manage and Assign Roles -> Manage Roles
2. Add roles for any of the following role types
- Global Roles: Allow you to set site wide permissions for the user
- Project Roles: Allow you to set project based role permissions for the user
- Slave Roles: 

#### Assign Roles
1. Navigate to Manage Jenkins -> Manage and Assign Roles -> Assign Roles
2. Assign roles for any of the following role types
- Global
- Project
- Slave
3. Once you add a user select the applicable roles

## Bonus: Run Jenkins in cli
Using the command line is required for building a continous integration system

1. Navigate to the downloaded jenkins.war file
2. Run `java -jar jenkins.war`
3. Go to Manage Jenkins -> Configure Global Security -> Enable Security should be checked
4. Go to http://localhost:8080/cli/
5. Download jenkins-cli jar file and place it in the location in which you plan to run the jenkins cli (this can be anywhere)
6. Navigate to the folder containing the downloaded jenkis-cli jar file and run the following command `java -jar jenkins-cli.jar -s http://localhost:8080/ help`