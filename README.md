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
