# my-network-architecture
This repo is overall my network structural design
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

https://d.docs.live.net/a46bfb26440cbb56/Desktop/my-network-architecture-master/Diagram/my_network_architecture.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

https://d.docs.live.net/a46bfb26440cbb56/Desktop/my-network-architecture-master/Ansible/filebeat-playbook.yml
This document contains the following details:
- Description of the Topology 
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build

### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting incoming traffic to the network.
- What aspect of security do load balancers protect? Solution: Availability
- What is the advantage of a jump box? Solution: When a jump box is used, its hidden benefit is that any tools in place for the SAN system are maintained on that single system. Therefore, when an update to the SAN management software is available, only a single system requires the update

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the path to the file and system failure.
- What does Filebeat watch for? Filebeat collects data about the file system.
- What does Metricbeat record? Metricbeat collects machine metrics, such
as uptime

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function         | IP Address | Operating system     |
|------------|------------------|------------|----------------------|
| Jump box   | Gateway          | 10.0.0.6   | Linux (ubuntu 18.04) |
| DVWA-VM1   | virtual computer | 10.0.0.7   | Linux (ubuntu 18.04) |
| ELK-Server | Security tool    | 10.0.0.10  | Linux (ubuntu 18.04) |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses 10.0.0.7

Machines within the network can only be accessed by private IP address.
- Which machine did you allow to access your ELK VM? DVWA-VM1 What was its IP address 10.0.0.7

A summary of the access policies in place can be found in the table below.

| Name       | Publicly accessible | Allowed IP addresses |
|------------|---------------------|----------------------|
| Jump box   | No                  | 10.0.0.7             |
| ELK-Server | No                  | 10.0.0.7             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible? It automates it and save time than doing manually each computers and also provides consistency.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
-configure ELK VM with docker
- install docker
- install python script language
- download and launch docker elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
https://d.docs.live.net/a46bfb26440cbb56/Desktop/my-network-architecture-master/Linux/docker_ps_output.png
### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- Specify which Beats you successfully installed: filebeat

These Beats allow us to collect the following information from each machine:
- : In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Syslog 
### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the configuration file to editor.
- Update the configuration file to include IP address
- Run the playbook, and navigate to status alert to check that the installation worked as expected.

Answer the following questions to fill in the blanks:
- Which file is the playbook? Installation Where do you copy it? In editor (nano)
- Which file do you update to make Ansible run the playbook on a specific machine? Installation file How do I specify which machine to install the ELK server on versus which to install Filebeat on? IP address
- Which URL do you navigate to in order to check that the ELK server is running? http://IP_address:5601
