# "ceg3120-p4-nreiner"  

ceg3120-p4-nreiner Project Readme File:  

## 1) Building the Container
* Once Docker is installed on your machine, you will want to select an image from Dockerhub (linked above) on which to build your container. 
  * For this project we are using [Apache](https://hub.docker.com/_/httpd).  

* Docker will provide you a code line to run for instantiating the basic container image
* To build your first container: 
  * Make sure to use the 'docker run' command and include '-dit'
  * Name the container with '--name [containerName]'
  * Bind the container to a port on the local machine with '-p [containerPort]:[machinePort]' 
  * Use the '-v' and "$PWD" in the command in order to make copies of the files appear in the :[cotainer-directory]  
* Personally, what I did, and you could do as well is to create the "Dockerfile" within your repository and edit the contents with a text editor  
  * The contents of the "Dockerfile" must contain a From and Run arguments for retreiving the correct image and running the desired installation commands  
  * Once you are sure that the container is in working order, and you have the "Dockerfile" all you need do is 'docker build -d' and 'docker run'  
* The last portion of this Milstone was just making sure that the Apache2 server we were utilizing pulls the contents from your '/html/index.html' file and displays the content at 127.0.0.1:[portValue]  

## 2) The mess that was AWS CLI  
* Due to a multitude of unforseen roadblocks this milestone was done partially on AWS, partially on PowerShell, and partially on DockerHub  

* For the creation of the AWS CLI aspect:
  * In order to make sure that the AWS CLI can run on my windows machine I went to [aws.amazon](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html) to download the 2nd version of the AWS CLI installer  
  * Where I was unable to do this inside AWS/Ubuntu Terminal, I turned to PowerShell and the executable file from the link above  
  * With the AWS CLi now installed, I could configure '~/.aws' on my personal machines PowerShell admin terminal  
  * Once I was sucessfully able to cd into this directory, I ran 'aws configure' which prompts the user for the desired information:  
	* The aws access key  
	* The aws secret access key  
	* The correct and current region 
	* The file type for output files 
  * Once I had finsihed inputting the correct information provided by Ms. Duncan on Pilot I was able to read 2 new files in '~/.aws'  
	* 'config'  
	* 'credentials'  
  * I didn't find out until afterwards that you can create and edit these files similar to the Dockerfile in Milestone 1  
  * Lastly, I ran the following command in PowerShell:  
	* 'aws ecr create-repository --repository-name (name of repository) --region (name of region)'  
  * This portion was picked up in DockerHub and GitHub Classrooms due to some of the aforementioned road blocks  

* With Ms. Duncan's guidance in lecture 4/19 I was able to head to [DockerHub](hub.docker.com) in order to create a free account similar to that of my GitHub account  
* With some personal research, and guidance from lecture the repository that was supposed to be finsihed with AWS CLI was finished in DockerHub by doing the following:  
  * Once I had created a DockerHub account I naviagted my way through the website to create my own repository, made sure that it was public and named the same name as my public GitHub repository that this README.md file is stored in  
  * Then, with the newly fucntioning repository, I went back to GitHub's desktop service and my public project 4 repository  
  * I was not sure whether the order mattered, but I went into the WorkFlow's Action tab first and created a workflow based on the template Ms. Duncan had linked us in the project 4 explanation  
  * Once I had created and pasted my .yml file into the workflow I made sure to alter the names of:  
	* The Username Secret
	* The Password Secret
	* The file path to the DockerHub repository  
  * I then took the information, remebering the names of the Secret's to my public github repository and added them in the settings->secrets for the perimissions to authenticate to DockerHub  
  * Once these changes were saved and committed they were pushed to main, and then pulled to the terminal instance of the repository on my unbuntu machine  
* Lastly, once the workflow was published I drafted a new release version and made sure that the tags were indeed appearing on my DockerHub repository. 

## 3) Images For Proof (Not Necessary, but felt they would add to the project)  
* Creation of Repository  
	* ![repoCreationImage](~/Project4/ceg3120-p4-nreiner/images/RepoCreation.JPG)  

* AWS CLI Error, reason for using DockerHub
	* ![awsErrorImage](~/Project4/ceg3120-p4-nreiner/images/awserror.JPG)  

* Credentials for AWS CLI in powershell  
	* ![credentialsCLIImage](~/Project4/ceg3120-p4-nreiner/images/credentials.JPG)  

* Proof that DockerHub is working as intended with GitHub classroom workflow
	* ![dockerHubImage](~/Project4/ceg3120-p4-nreiner/images/dockerproof.JPG)

