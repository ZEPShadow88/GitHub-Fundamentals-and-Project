# GitHub-Fundamentals-and-Project
Project and Homework 13
## Automated ELK Stack Deployment

Zachery Parker
The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _playbook(see ansible folder): Ansible/ELK.yml https://github.com/ZEPShadow88/GitHub-Fundamentals-and-Project/blob/main/Ansible/elk.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly versatile, in addition to restricting high traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- _TODO: What does Filebeat watch for?_
- _TODO: What does Metricbeat record?_

- ANSWER: 

  Filebeat keeps track of the log files or places that the user specifies, collects log events, and indexes them in Elasticsearch or Logstash. Metricbeat Metrics from your systems and services can be retrieved. It's a simple way to communicate system and service information. From the CPU to the RAM, from Redis to NGINX, and so on.   

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| JPG-1    | Gateway  |20.37.254.162| Linux           |
| Web-1    | DVWA     |10.1.0.5    | Linux            |
| Web-2    | DVWA     |10.1.0.6    | Linux            |
| ELK-VM   | Server   |10.2.0.4    | Linux (Kibana    |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the ELK Server machine, (Elk-VM) machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses 20.37.254.162.

Machines within the network can only be accessed by JPG-1.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| JPG-1    | Yes                 | 10.0.0.1 10.0.0.2    |
| Web-1    | No                  | 20.70.5.45           |
| Web-2    | No                  | 20.70.5.45           |
| ELK-VM   | Yes                 | 20.58.172.93         |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because... Using Ansible to automate configuration has the advantage of increasing efficiency while configuring several systems.
- _TODO: What is the main advantage of automating configuration with Ansible? There are no security codes that must be entered. All you have to do is list all necessary tasks in a playbook, and Ansible will handle the rest.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; 
- Install Docker.io
- Install Docker Module
- Increase Virtual Memory
- Download and launch elk container
- Enable elk ports
- Download and launches the sebp/elk container over ports `5601`, `9200`, and `5044`.

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(docker-ps-output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring
- 10.1.0.4
- 10.1.0.5
- 10.1.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
- Metricbeat
- Filebeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc.
- Using Elasticsearch or Logstash, Filebeat collects log events and indexes them. Metricbeat keeps track of system metrics by monitoring the operating system and system services. Putting the Playbook to Work

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the my-playbook.yml file to playbook.
- Update the my-playbook.yml file to include host: webservers
- Run the playbook, and navigate to curl localhost/setup.php to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?
- /etc/ansible/
- _Which file do you update to make Ansible run the playbook on a specific machine?
- update the (ansible-config) 
-   How do I specify which machine to install the ELK server on versus which to install Filebeat on?
- update the hostname in the hosts file and then update the (ansible-config) file and then save.
- _Which URL do you navigate to in order to check that the ELK server is running?
-http://20.58.172.93:5601
_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
