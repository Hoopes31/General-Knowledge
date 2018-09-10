# Jenkins pipeline

Introduction to setting up a Jenkins Pipeline

This overview is based on a _[video](https://www.youtube.com/watch?v=ndLbn24OwQg&t=134s)_ by Raghav Pal

## Setting up the Delivery Pipline

Setting up the pipeline view, creating default triggers 

1. Download and install the **Delivery Pipeline Plugin** via the Jenkins Plugin Manager
2. Select the + button on the Jenkins Jobs Table
3. Name & Create a new **Delivery Pipeline View**
4. Scroll down the redirected page and set up a component
5. Fill out the **Name** & **Initial Job** field (This sets the created pipelines main starting point)
6. Set the **Enable start of new pipeline build** checkbox to true (Allows jobs to be triggered from the pipeline view table)

_There are quite a few customization options under the **Edit View** menu that are worth checking out_ 😊

## Setting up the Build Pipeline

1. Download and install **Build Pipeline** via the Jenkins Plugin Manager
2. Select the + button on the Jenkins Jobs Table
3. Name & Create a new **Build Pipeline View**
4. Set the **Select Initial Job** to your initial job
5. Set the **No Of Displayed Builds** to the number of build pipelines you wish to see

## Email notifications

Enables email notifications to be sent in as post build actions

1. Manage Jenkins -> Configure System: Scroll down to E-mail Notifications
2. Fill out the **SMTP server** input field
3. Click advanced
4. Set checkbox Use SMTP Authentication = true
5. Fill out the **User Name** and **Password** fields
6. There is an option to test this by checking the **Test configuration by sending test email**
7. Navigate to any of your jobs and set up a post build action **E-mail Notification**
- Here you can select recipients and set email conditions