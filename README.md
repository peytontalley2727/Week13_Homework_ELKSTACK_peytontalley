# Week13_Homework_ELKSTACK_peytontalley
ELK Project week 13 Peyton Talley
## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _______ file may be used to install only certain pieces of it, such as Filebeat.
Tailback_Sweep.yml
  - _TODO: Enter the playbook file. 

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network. protected:traffic
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_    availibility of the network:  ability to keep a device protected from someone logging in without a specific ssh key.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.  Logs;Traffic
- _TODO: What does Filebeat watch for?_     Filebeat watches and monitors the log files or locations that users specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing. Filebeat is a lightweight shipper for forwarding and centralizing log data. Installed as an agent on the server.

- _TODO: What does Metricbeat record?_    Metricbeat is a lightweight shipper that records and periodically collects metrics from the operating system and from services running on the server and takes the metrics and statistics that it collects and ships them to the output that users specify, such as Elasticsearch or Logstash.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function   | IP Address     | Operating System |
|----------|------------|----------------|------------------|
| RedTeam  | Gateway    | 52.165.24.163  | Linux            |
| Web-1    | Server     | 10.0.0.9       | Linux            |
| Web-2    | Server     | 10.0.0.10      | Linux            |
| Elk-Vm   | Monitoring | 104.215.101.35 | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __RedTeam___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 
- _TODO: Add whitelisted IP addresses_ My personal IP

Machines within the network can only be accessed by __RedTeam___.
- _TODO: Which machine did you allow to access your ELK VM? RedTeam VM What was its IP address?_ 52.165.24.163

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| RedTeam  |     Yes             |    My Personal IP    |
| Web-1    |     No              |    10.0.0.4          |
| Web-2    |     No              |    10.0.0.4          |
| Elk-VM   |     No              |    10.0.0.4          |
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because... sealed from vulnerabilities
- _TODO: What is the main advantage of automating configuration with Ansible?_

Free: Ansible is an open-source tool.
Very simple to set up and use: No special coding skills are necessary to use Ansible's playbooks.
Powerful: Ansible lets user model even highly complex IT workflows.
Flexible: User can orchestrate the entire application environment no matter where it’s deployed. Users can also customize it based on their needs.
Agentless: User don’t need to install any other software or firewall ports on the client systems it want to automate. User also don’t have to set up a separate management structure.
Efficient: Because user don’t need to install any extra software, there’s more room for application resources on the server.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._

Install docker.io
Install pip3
Install Docker python module
Increase virtual memory
Download and launch a docker


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)
https://drive.google.com/file/d/19SqYwlIV2x07UNO3Ib4VRvqjxRnpXr8C/view?usp=sharing


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_


   | Name  	    |   	| IP Address 	|
   |-------	    |-----------|------------	|
   | Web-1 	    |   	| 10.0.0.9   	|
   | Web-2 	    |   	| 10.0.0.10   	|
  





We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_ Filebeat; Metricbeat

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Filebeat - collects data about the file system such as log events, and ships them to the monitoring cluster.
Metricbeat - collects metrics and statistics and ships them to the output that was specified, such as Elasticsearch or Logstash.



### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the ___Playbook__ file to __Ansible___.
- Update the ___Host__ file to include... webservers and ELK
- Run the playbook, and navigate to __Kibana__ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
