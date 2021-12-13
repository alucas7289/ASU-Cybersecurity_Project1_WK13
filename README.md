# ASU-Cybersecurity_Project1_WK13
Ansible YAML Scripts; Bash Scripts; Network Diagram
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/Azure_CloudSecurity_Network_Diagram_HW12.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ¬¬¬¬____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file. /etc/ansible/elk-playbook.yml


This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting traffic to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?

-Load Balancers protect/defend network traffic from denial-of-service (DDoS)attacks.
-The advantage of utilizing a jump box server is that it acts as a single point of management for tools placed in the network zone. 


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- _TODO: What does Filebeat watch for?
- _TODO: What does Metricbeat record?

-Filebeat monitors the log files and log events and forwards these to Elasticsearch.
-Metricbeat records data from your servers along with services running on the servers. This data can be pointed or sent to Elasticsearch. 


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.4   | Linux            |
| Web-1    | Server   | 10.1.0.5   | Linux            |
| Web-2    | Server   | 10.1.0.6   | Linux            |
| Elk-VM   | Server   | 10.0.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

-Home Public IP


Machines within the network can only be accessed by Jump-box.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_

-Jump Box has access to the Elk-VM
-Jump Box IP is 10.1.0.4


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible 	| Allowed IP Addresses 	|
|----------|----------------------	|---------------------------	|
| Jump Box | Yes				| Home IP 70.xxx.xxx.xxx/32	|
| Web-1    | No				| 10.1.0.4                 	|
| Web-2    | No				| 10.1.0.4                 	|
| Elk-VM   | No				| 10.1.0.4 				|

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

-Automating configuration processes with Ansible gives the admin the ability to utilize infrastructure as a code (IAC) which can speed up the provisioning processes for user access. 


The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
•	Install Docker.io
•	Install Python3-pip
•	Install Docker Module
•	Increase Virtual Memory
•	Download and Launch a Docker Elk Container


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/Elk_dock_ps_screenshot.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

-Web-1 Server 10.1.0.5
-Web-2 Server 10.1.0.6


We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

-Both Filebeat and Metricbeat have been installed on both machines


These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

-Filebeat collects the log files and log events.
-Metricbeat collects data from your servers along with metrics of services running on the servers. 
 
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_

Which file is the playbook? Where do you copy it? 
-/etc/ansible/filebeat-config.yml
Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?
-/etc/ansible/hosts
-Add the machines IP to the webserver module in the hosts file
Which URL do you navigate to in order to check that the ELK server is running?
-http://20.124.32.127:5601/app/kibana#/home
