## CONFIGURED DYNAMIC JENKINS SLAVE ON AWS 

- Update the vars/secret.yaml :  
	
	- Provide your AWS_ACCESS_KEY_ID AND AWS_SECRET_KEY_ID

- Update the vars/details.yaml:
	
	- Provide the SUBNET_ID , KEY_NAME, SECURITY_GROUP_ID

- Update the path of the private key in the ansible.cfg file 


- You can either use my dockerimage :  
  - Name:  raghav1674/arthjenkinsslave:v3 
	
	OR 
  inorder to build your image which should work as JENKINS_SLAVE:

	- image should have java installed and ssh server running

- I have included the Dockerfile in files/ folder , just download the java and mvn and copy in files/ folder and build your own image 

- [JAVA](https://www.oracle.com/in/java/technologies/javase-downloads.html)
        
- [MAVEN](https://downloads.apache.org/maven/maven-3/3.6.3/binaries/apache-maven-3.6.3-bin.zip)
