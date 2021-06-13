## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

https://github.com/JefferyFerris100/Project1-06-02-21/blob/main/Ansible
  

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly deliverable, in addition to restricting access to the network.
- The Load Balancer protects the network from denial of service attacks by distributing traffic to the multiple servers.
- The advantage of the Jump-Box is to give controlled access to the servers thru one device.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system applications.
Filebeat watches log data and collects log events from the server.
Metricbeat records data from the system and services running on the server.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function                               | IP Address      | Operating System |
|------------|----------------------------------------|-----------------|------------------|
| Jump-Box   | Gateway w/Ansible                      |52.255.185.190   | Linux            |
| VM-jaf     | Hosts Elk Stack                        |20.94.49.144     | Linux            |
| VM-Web-1   | Hosts Docker w/ Filebeat & Metricbeat  |10.0.0.5         | Linux            |
| VM-Web-2   | Hosts Docker w/ Filebeat & Metricbeat  |10.0.0.6         | Linux            |
| VM-Web-3   | Hosts Docker w/ Filebeat & Metricbeat  |10.0.0.7         | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump-Box-Provisioner machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 10.0.0.0/16


Machines within the network can only be accessed by Jump-Box.
The Jump-Box-Provisioner with IP: 55.255.85.190 has access to the ELK virtual machine

A summary of the access policies in place can be found in the table below.

| Name         | Publicly Accessible | Allowed IP Addresses |
|--------------|---------------------|----------------------|
| Jump-Box     | Yes                 | 10.0.0.0/16          |
| VM-Web-1     | No                  |                      |
| VM-Web-2     | No                  |                      |
| VM-Web-3     | No                  |                      |
| VM-jaf-Elk   | No                  |                      |


### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
Ansible automation tool allows easy configuration of servers with software deployment, provisioning, management etc.. 


The playbook implements the following tasks:
- Install docker.io
- Install python3-pip
- Install docker module
- Increase virtual memory
- Download and launch a docker elk container


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- IP: 10.0.0.5
- IP: 10.0.0.6
- IP: 10.0.0.7

We have installed the following Beats on these machines:
Filebeat and Metricbeat 

These Beats allow us to collect the following information from each machine:
Filebeat monitors the log files and collect log events and
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
