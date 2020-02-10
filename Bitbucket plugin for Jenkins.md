# Bitbucket plugin for Jenkins

Bitbucket plugin offers integration between Bitbucket and Jenkins, which can be installed from Jenkins market place.

## How does it work

It exposes a single URI endpoint that you can add as a WebHook within each Bitbucket project you wish to integrate with. This single endpoint receives a full data payload from Bitbucket upon push (see their documentation), triggering compatible jobs to build based on changed repository/branch.

**Note:**  Bitbucket automatically injects the payload received by Bitbucket into the build. You can catch the payload to process it accordingly through the environmental variable $BITBUCKET_PAYLOAD.

## How to do it

1. Install the bitbucket plugin from jenkins market.![Bit bucket plugin image](./images/bitbucket%20plugin%20img.png "Bitbucket Plugin image")

2. Configure bitbucket repository with a webhook. 

   - Go to your repository which you want build in jenkins.

   - Go to settings of that repository and look for webhooks option.

   - Click on add webhook and Enter 

     - A title

     - URL (Jenkins URL Ex: http://\<jenkins_url>/bitbucket-hook/)

     - Check status **Active** and make sure Triggers is set to **Repository push** and **Save**

       Bitbucket Webhook Configuration. ![Bitbucket webhook config](./images/bitbucket%20webhook.png "Bitbucket Webhook Configuration")
       


## For private repositories make sure you do this extra step(anyone can be done):

1. Go to Terminal and switch to Jenkins user and generate ssh key, leave everything default and don't enter passphrase.

   ```bash
   sudo su jenkins
   ssh-keygen
   ```

2. Display the public key of your ssh key.

   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
   
3. Go to your bitbucket account settings and add SSH key (not your repository).

   - In security section select SSH keys. 
   - Click add key and Enter a label.
   - Copy and paste the public you displayed in the terminal in key field and save.![Bitbucket ssh key Screenshot](./images/ssh%20key%20bitbucket.png "Bitbucket ssh key page")

4. Display the secret key and add in Jenkins.
   - `cat ~/.ssh/id_rsa`
   - Open jenkins and Go to Credentials and add global credentials.
   - Change the kind to **SSH Username with private key**.
   - Give ID and name and in private key option select Enter directly and paste the private key you just displayed.!["Jenkins SSH Key"](./images/ssh%20key.png "SSH Key")

------

**Note:** If using this step Make sure you have a separate user for jenkins for safety purpose. 

1. Open Jenkins and go to Credentials and add global credentials.
2. add the bitbucket username and password and give it a Unique ID and Save the Credentials.!["Jenkins Credentials Page"](./images/usr%20and%20pwd%20cred.png "Jenkins Credentials Page")

## Creating a Sample Job

1. Click on New Item.

2. Select Free style project and Enter a Project name and click enter.

3.  Then, in configurations go to **Source Code Management** and select which SCM you're using and enter the repository URL(give **SSH** URL if you added SSH key as credentials else **HTTP** if you added username and password as credentials) and select the credentials which you created.

4.  next, In build triggers select **Build when a change is pushed to BitBucket.**

5. In build section add your build steps

6. Save and run the job to check if it's able to build.

7. Now, try doing some changes to the code and pushing now it must automatically trigger the job when changes are pushed to repository.

------

**Note:**

   1. Make sure your Jenkins Server is accessible from the Internet as the bitbucket  does a POST request to Jenkins server it is important to make it available to access from outside the network.
   2. Adding credentials part is important only if you are working with private repositories.
   3. Make sure the Jenkins user has pull permission from the repository.

**References:**

1. [Bitbucket Plugin](https://plugins.jenkins.io/bitbucket/) 
