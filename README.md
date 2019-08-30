# Ansible-kubernetes-cluster

#### Prerequisites

  1. 3 or more server running Ubuntu 18.04 LTS (1 server for Master and 2+ servers for worker nodes) with atleast 2GB RAM and 2 vCPU each. The more RAM and CPU for worker node will help to run more applicatons
  2. Ansible installed in your machine https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
  3. git installed in your machine
  
#### Step 1 

Clone the repository
 
 ``` git clone https://github.com/thiyaguin/Ansible-kubernetes-cluster.git ```
 
#### Step 2
 
Update the Ansible-kubernetes-cluster\hosts file with IP addresses of Master and workers nodes
 
#### Step 3 

Update the CreateK8SCluster.yml - iprange section with IP CIDR block
 
#### Step 4 

Run the play book 
 
 ``` ansible-playbook -i hosts CreateK8SCluster.yml ```
 
 The play book will create user k8admin and enable password less access between other servers. This user will be used to run the cluster 
 
 #### Step 5 
 
 To Validate the cluster ssh to the Master node and run the following commands
 
 Switch as kadmin user
 
 ``` sudo su kadmin ``` 
 
 Run the kubectl command to get node status
 
 ``` kubectl get node ```
 
The command will return all the nodes informations

#### Thank you 

You can start deploying the application in the cluster. To know more about deploying application follow https://kubernetes.io/docs/home/
