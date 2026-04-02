# Python-flask
Flask is a lightweight, flexible micro web framework for Python, ideal for small-to-medium web applications and APIs. It provides core tools for routing and templating (using Jinja) while allowing developers to plug in extensions for databases or form validation as needed. 

<img width="386" height="215" alt="Image" src="https://github.com/user-attachments/assets/898ca040-e2c3-43f5-bf3d-33cd5cd97b80" />

<img width="241" height="235" alt="Image" src="https://github.com/user-attachments/assets/93dff63d-33e4-4441-80a6-6a40a32ca5a4" />


# This is the homepage of Apache2 webserver
<img width="601" height="434" alt="Image" src="https://github.com/user-attachments/assets/0e25b9d2-ea96-41e9-bf39-8ac3ccf83014" />


# This is the homepage of nginx webserver
<img width="436" height="193" alt="Image" src="https://github.com/user-attachments/assets/c54cc5f4-110e-4999-9a73-e98a17e7ac24" />


# This is installing Jenkins on AWS  
<img width="718" height="331" alt="Image" src="https://github.com/user-attachments/assets/5ff11fdf-ee8c-4373-b6f4-0bbef1c9205a" />

# Docker permission denied
sudo chmod 777 /var/run/docker.sock

# How to build a docker image
docker build -t abiimage .

# For requirements.txt - to collate all the libraries used for the project
pip freeze >> requirements.txt

Project narrative:
The project aim is to build docker images from the python application and pushing it to the docker hub using the cicd pipleline in Jenkins, whilst ensuring there is integration between Docker hub and Jenkins. 

## Project tools used:
1. EC2, EC2 connect, Security group,

2. Jenkins Software (for CICD process),

3. Docker Hub

4. Python/flask

## Project workflow:
# Step 1:

Launch a Jenkins server from EC2 instance:

1. Log into AWS console and launch an EC2 instance

2. Create a free tier ubuntu server

3. Add a security group  - Edit inbound rules for Jenkins on port 8080

4. Launch EC2 connect

# Step 2:

Update the system to install Jenkins with the prompts below:

5. sudo apt update -y

Install Jenkins

6. vi Jenkins.sh
7. Run Jenkins file (using code saved on vs code).

Ctrl c

8. Press Esc on keyboard, then type :wq!

9. Type chmod 777 Jenkins.sh

10.Type ./Jenkins.sh

To check is Jenkins is install on server:
11. Type sudo systemctl status Jenkins

12. Go back to the EC2 instance and copy the Public IP4 address

13. Paste in a browser and add :8080 press enter
14. In the Jenkins brower, copy the red link for admin password

15. Go to the EC2 browser, clear the terminal and type sudo cat right click and paste the red link

16. copy the password and paste in the Jenkins browser

Step 3:
Install docker in the Jenkins server
17. Type docker --version

18. copy and paste the sudo apt install docker io

18b. Give Docker permission with Jenkins server

Docker permission denied

sudo chmod 777 /var/run/docker.sock

Step  4:
Once in Jenkins CICD:

19. Click on install suggested plug ins

20. Type username and password: bims Iwaro123

21. On Install config, click save and finish, start using Jenkins.

Once in the Jenkins env:
22. Click on the Manage Jenkins wheel

23. Click on Plugins, select Available Plugins

24. In the search box, type Docker

25. Select Docker and Docker pipelines, click Install

26. Click on Jenkins

27. Click on the Manage Jenkins wheel

28. Click on credentials

29. For system, make sure Global is selected.

30. Click on add credentials

31. Click on secret text,  then next

32. In the secret column, type in my docker password = iwaro125!

33. In ID, type in dockerID (copy and paste this from vs code)

34. click create

35. Click on Jenkins, click New item

36. Enter item name e.g. Test-Jenkins6, click on pipeline, click ok

37. In description, type e.g Demo 6

38. Select GitHub project

39. Copy and paste the GIT HUB url of the python application

40. Put a / behind the url

41. For pipeline, select Pipeline script from SCM

42. For SCM, select Git from the dropdown.

43. Paste the GitHub url and add / for repository URL

44. Change Branch specifier to "Main" according to what it is in Git hub

45. Click on Apply and save.

46. Click on Build now and click on Generative link

47. Click on Console output.

Step 5:
Luanch Docker Hub

48. Once Jenkins is successfully working, go to google and bring up Dockerhub login.

49. The images built will appear in the docker hub.

## Project Challenges:
 Docker not  found
 Jenkins installation not running
 Wrong Docker password

## Project Solutions:

Docker not found:

Docker was installed on the Jenkins server:
docker --version
sudo apt install docker io

Docker permissions to Jenkins was installed:
sudo chmod 777 /var/run/docker.sock

Jenkins installation not running:
Jenkins manage pipeline steps was reviewed and corrected.

Wrong Docker password:
The correct Docker password was applied.