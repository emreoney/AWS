# AWS Projects

# IAM

## What is AWS IAM?
AWS Identity and Access Management (IAM) is a service that helps yousecurely control access to AWS resources. It allows you to manage who canaccess your AWS services and resources, what actions they can perform, andunder what conditions.

## How I'm using AWS IAM in this project
I've created an IAM Group which allows to make everything about EC2's whichhave development tag. After that, I've created an user to test my policy.

## Tags
In real life, there might be many instance in your instances page. Tags helps usto categorize our instances. For example, you can just see the instances whichare working in production and development.
The tag I’ve used on my EC2 instances is called Env. The value I’ve assignedfor my instances are Production and Development

![image](https://github.com/user-attachments/assets/dfe7d0cc-1a43-4413-9fa8-e16433626725)


## IAM Policies
IAM Policies are rule set for our resources in AWS. We can set that "Who canaccess to my resources and What he can do" with IAM.

The policy I set up
For this project, I’ve set up a policy using JSON. It is allowed to start, terminate or something else about EC2, but you can do it ifthe EC2 has tag "development".

My JSON Policy:

![image](https://github.com/user-attachments/assets/dfee85ec-cf92-43e6-9873-4ad16d9dfc49)



I created an user group and attached the policy this user group. Then, I created an user and attached him to user group which I created.

Logging in as an IAM User

![image](https://github.com/user-attachments/assets/7c0ad23b-4861-4e3f-b09e-3b9c25b537f3)


Testing IAM Policies
Stopping the production instance:

![image](https://github.com/user-attachments/assets/182aad36-6076-467a-bdc4-ef850c8e5db0)

Stopping the development instance

![image](https://github.com/user-attachments/assets/b960c2de-ad85-4182-97d1-055eae119867)






# EFS

File Object is a data storage system.

Advantages over EBS:

- Flexible structure. As the file size increases, the size of EFS increases, and as the file size decreases, the size of EFS decreases.
- It can be accessed by more than one machine at the same time.
- It is not a disc. No operating system is installed on it.

The logic of operation is as follows:

For example, we have 2 virtual servers. These servers are entered and a folder with the name we want is created. For example, we created a folder named efs in 2 servers. Then these folders are mounted with the efs drive. After this process is done, everything written, added, etc. to the efs folders in the servers is also added to the efs drive.


1- I connect to my first virtual server and create a folder named efs in it.

![image](https://github.com/user-attachments/assets/ff1387e7-3312-4a7a-bb0a-ab718f6d02d6)


2- I install amazon-efs-utils into the server. 
sudo yum install amazon-efs-utils

3- I mount the efs folder with the efs drive. To get the mount command, you must enter the EFS you created in AWS and press the attach button.

![image](https://github.com/user-attachments/assets/7cc432d3-820c-404a-9a91-fe4ee87aff64)

Copy the command in the window that opens and use the command in the virtual server you are connected to.

![image](https://github.com/user-attachments/assets/9b5623a3-53a1-4202-80b5-3cf6458456e2)


4- Now I will connect to the other server, create a folder named efs on it, mount it with the efs drive and check whether I can see the file I added on the emre-s2 server or not.

The file I created in emre-s2 server.

![image](https://github.com/user-attachments/assets/3d0e791f-8923-4f26-a558-5f660e950c11)


5- I connected to the emre-s1 server, created a folder named efs in the same way and mounted it with the efs drive. After mounting, when I looked inside the folder, I could see the file and its contents that I added from the other server.

![image](https://github.com/user-attachments/assets/3caf7268-4096-46f2-a440-835f36688858)




