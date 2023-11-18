# Jenkins-demo
Implementation of Jenkins, Right from Installation, Configuration and Deployment of multiple applications.

# Install Jenkins

# Pre-Requisites:
Java (JDK)

# Run the below commands to install Java and Jenkins:
Install Java:

sudo apt update
sudo apt install openjdk-11-jre

# Verify Java is Installed:

java -version

# Install jenkins using script

# Login to Jenkins using the below URL:
http://localhost:8080

After you login to Jenkins, - Run the command to copy the Jenkins Admin Password - sudo cat /var/lib/jenkins/secrets/initialAdminPassword - Enter the Administrator password

# Click on Install suggested plugins
# Wait for the Jenkins to Install suggested plugins
# Create First Admin User 

# Install the Docker Pipeline plugin in Jenkins:
Log in to Jenkins.
Go to Manage Jenkins > Manage Plugins.
In the Available tab, search for "Docker Pipeline".
Select the plugin and click the Install button.
Restart Jenkins after the plugin is installed.

Wait for the Jenkins to be restarted.

# Docker Slave Configuration
Run the below command to Install Docker

sudo apt update
sudo apt install docker.io

# Grant Jenkins user and Ubuntu user permission to docker deamon.
sudo su - 
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker

Once you are done with the above steps, it is better to restart Jenkins.

http://localhost:8080/restart

The docker agent configuration is now successful.

