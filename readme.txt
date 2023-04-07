1.Create a new Docker volume for Jenkins data by running the following command.
docker volume create jenkins-data

2.Start a new Jenkins container with the following command (Replace <new_container_name> with the name you want to give to the new container).
docker run -d -p 8080:8080 -p 50000:50000 --name <new_container_name> -v jenkins-data:/var/jenkins_home jenkins/jenkins

3.Wait for the new container to start up, and then access the Jenkins web interface by opening a web browser and navigating to http://<your_server_ip>:8080.

4. Get initialAdminPassword running the following command.
docker logs <container_id>
Jenkins initial setup is required. An admin user has been created and a password generated.
Please use the following password to proceed to installation:

c75abea0afb3485b8490a6ed15dd25a0 <<-----This

This may also be found at: /var/jenkins_home/secrets/initialAdminPassword

*************************************************************
*************************************************************
*************************************************************

5. Follow the on-screen instructions to set up the new Jenkins instance, including creating a new admin user with a new password.
