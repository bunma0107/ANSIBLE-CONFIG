# ANSIBLE-CONFIG

ANSIBLE CLIENT AS A JUMP SERVER (BASTION HOST)

A Jump Server(Bastion Host) is an intermediary server through which access to internal network can be provided. In the current architecture we have been working on, the webservers are inside a secured network which cannot be reached directly from the Internet. To access the webservers using SSH, we need to go through a jump server which provides a better security and reduced attack.

In the diagram below, the Virtual Private Network (VPC) is divided into two subnets – Public subnet has public IP addresses and Private subnet is only reachable by private IP addresses.

![image](https://user-images.githubusercontent.com/113097621/225132002-a79333c8-971c-4626-95eb-e69a0a814def.png)

Install and configure Ansible on EC2 Instance

![image](https://user-images.githubusercontent.com/113097621/220458969-f3e4404b-2450-4178-ad42-4bc1f03690a4.png)

Check your Ansible version by running ansible --version

![image](https://user-images.githubusercontent.com/113097621/220459151-ae55f158-38a0-4bf8-9abb-e68bd8aef2b5.png)


Configure Jenkins build job to save your repository content every time you change it – this will solidify your Jenkins configuration skills acquired in Project 9.


![image](https://user-images.githubusercontent.com/113097621/220472156-cf92143d-08b5-4a55-87e9-073840966253.png)


![image](https://user-images.githubusercontent.com/113097621/220474071-6d5384a5-3935-4d8e-8546-f5f27c983328.png)


Test your setup by making some change in README.MD file in master branch 

![image](https://user-images.githubusercontent.com/113097621/220472002-1d47bc0c-1df7-4833-8651-81bc9deed0fa.png)

![image](https://user-images.githubusercontent.com/113097621/220481059-94a535e5-3e18-4e0b-a617-d16f6aac23c9.png)

Prepare your development environment using Visual Studio Code

![image](https://user-images.githubusercontent.com/113097621/220483757-c2533030-21d8-4fb0-af96-8a1fa8ce2a62.png)

Begin Ansible Development

In your ansible-config-mgt GitHub repository, create a new branch that will be used for development of a new feature.

![image](https://user-images.githubusercontent.com/113097621/220485337-6f94b687-92a2-4192-99cb-ad60ee5268df.png)



![image](https://user-images.githubusercontent.com/113097621/220487445-2fccbb89-0064-42c2-a739-3847a190fd1f.png)


Within the inventory folder, create an inventory file (.yml) for each environment (Development, Staging Testing and Production) dev, staging, uat, and prod respectively.
![image](https://user-images.githubusercontent.com/113097621/220770145-2aac6184-02db-4555-b11a-9ec616e43bfc.png)

TEST SSH into NFS
![image](https://user-images.githubusercontent.com/113097621/223494763-dd397223-8fcf-42f5-92d0-1c6c975ce4b1.png)

TEST SSH into DB
![image](https://user-images.githubusercontent.com/113097621/223495018-757bd094-883b-48cf-9411-75c7bc326c3a.png)


Update your inventory/dev.yml file with this snippet of code:
![image](https://user-images.githubusercontent.com/113097621/223495246-ce20e148-a420-4f64-8aa4-99bcf700e63b.png)

Create a Common Playbook
Update your playbooks/common.yml file with following code:
![image](https://user-images.githubusercontent.com/113097621/223495785-d744b82a-4c70-4603-88b2-0d475b8ae463.png)


Commit your code into GitHub:

    use git commands to add, commit and push your branch to GitHub
    
   ![image](https://user-images.githubusercontent.com/113097621/223503620-e2fee8ca-4eb6-4fa0-b250-59f1ad1f212c.png)
    
   ![image](https://user-images.githubusercontent.com/113097621/223503778-ae710d33-fec9-4c69-b053-f1cd3800c6c3.png)
    
   ![image](https://user-images.githubusercontent.com/113097621/223504142-f0b48de7-18c0-473a-b7cd-67e83aa661e8.png)

    
   ![image](https://user-images.githubusercontent.com/113097621/223504031-0d71c4c9-347d-49cb-8e06-1b285e402dd6.png)
    
    Create a Pull request (PR)
    
   ![image](https://user-images.githubusercontent.com/113097621/223504425-ea5862d0-52bb-4600-b689-4af7c2a0dd6e.png)
    
   ![image](https://user-images.githubusercontent.com/113097621/223504659-d7832c75-b33c-4261-9a6b-e7984562626d.png)


![image](https://user-images.githubusercontent.com/113097621/223505037-39dafd82-d0b8-4b11-8d2e-3ace8658ad90.png)

Confirm our changes runs on Jenkins
![image](https://user-images.githubusercontent.com/113097621/223505835-b159c45e-4288-4c1a-9783-fbffee4bced7.png)

![image](https://user-images.githubusercontent.com/113097621/223506172-19d4368c-a166-4b7d-802d-4f38296ad9fe.png)

Once your code changes appear in master branch – Jenkins will do its job and save all the files (build artifacts) to /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/ directory on Jenkins-Ansible server.

![image](https://user-images.githubusercontent.com/113097621/223507128-f144e489-b463-4785-91f8-342943296fca.png)

![image](https://user-images.githubusercontent.com/113097621/223507923-7017011f-aea1-470f-ad54-9d1c12ddf080.png)


Test

Save Artifacts

ansible-playbook -i inventory/dev.yml playbooks/common.yml

![image](https://user-images.githubusercontent.com/113097621/225092126-56338850-4d82-405a-ab9a-e3d5e62779b3.png)


check if wireshark has been installed by running which wireshark or wireshark --version

   ![image](https://user-images.githubusercontent.com/113097621/225126695-49ff9edc-833e-4f14-8852-af857354fa79.png)

    
This project architecture looks like this 
![image](https://user-images.githubusercontent.com/113097621/225131605-33205550-887b-4ee8-b7da-47680849cb53.png)
    




