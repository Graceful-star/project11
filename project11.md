# Documentation of Project11
## Step 1
1. I updated the name tag on my ec2-instance from "Jenkins" to "Jenkins-ansible"

![ubuntu](images/image1.PNG)

2. I created a new repository in my Git-hub account and named it "ansible-config-mgt"

![ubuntu](images/image2.PNG)

3. I installed Ansible
  
   `sudo apt update`

   `sudo apt install ansible`

   ![ubuntu](images/image3.PNG)
   ![ubuntu](images/image4.PNG)

4. I checked my ansible version

   `ansible --version`

   ![ubuntu](images/image5.PNG)

5. I created a new freestyle project in my Jenkins server and named it "Ansible"

   ![ubuntu](images/image6.PNG)

6. I configured webhook in Github

   ![ubuntu](images/image7.PNG)

7. I tested my setup

   ![ubuntu](images/image8.PNG)
   ![ubuntu](images/image9.PNG)
   
   `ls /var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/`
   ![ubuntu](images/image10.PNG)

## Step 2
1. I cloned down my ansible-config-mgt repository to my jenkins instance
    
    ![ubuntu](images/image11.PNG)

2. I created a new branch in my cloned repository

   ![ubuntu](images/image12.PNG)
   ![ubuntu](images/image13.PNG)
   ![ubuntu](images/image14.PNG)

3. I created a directory and named it 'playbooks'
   
   ![ubuntu](images/image15.PNG)

4. I created another directory and named it 'inventory'

   ![ubuntu](images/image16.PNG)

5. Within the inventory folder, I created an inventory file for each environment.

    ![ubuntu](images/image17.PNG)

6. I created a playboook in playbooks folder and named it 'common.yml'

7. I imported my key into ssh-agent and confirmed it
   
   eval `ssh-agent -s`

   `ssh-add private key`

   `ssh-add -l`

   ![ubuntu](images/image18.PNG)

8. I ssh into my server using my ssh agent

    `ssh -A ubuntu@public-ip`

    ![ubuntu](images/image19.PNG)
     ![ubuntu](images/image20.PNG)

9. I updated my inventory/dev.yml file with the required code

     ![ubuntu](images/image21.PNG)

10. I did likewise for playbook/common.yml

## Step 3
1. I commited my code into github

   `git status`
   `git add .`
   `git commit -m "make changes"`
   `git push`

   ![ubuntu](images/image22.PNG)
   ![ubuntu](images/image23.PNG)
   ![ubuntu](images/image24.PNG)

2. I created a pull request and merged it with the main branch
  
  ![ubuntu](images/image25.PNG)
  ![ubuntu](images/image26.PNG)

3. I confirmed if the changes has been made

    ![ubuntu](images/image27.PNG)
    ![ubuntu](images/image28.PNG)


## Step 4
1. I verified my playbook code and confirmed that it was working.

  `ansible-playbook -i inventory/dev.yml playbooks/common.yml`

  ![ubuntu](images/image30.PNG)

2. I checked each server to see if wireshark was running

   `wireshark --version`
   ![ubuntu](images/image31.PNG)
   ![ubuntu](images/image32.PNG)
   ![ubuntu](images/image33.PNG)
   ![ubuntu](images/image34.PNG)
   ![ubuntu](images/image35.PNG)