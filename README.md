# ElkProject
The files in this repository were used to configure the network depicted below.

elk diagram.png

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

/etc/ansible/files

This document contains the following details:

Description of the Topologu
Access Policies
ELK Configuration

Beats in Use
Machines Being Monitored


How to Use the Ansible Build


Description of the Topology
The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.
Load balancing ensures that the application will be highly _____, in addition to restricting _____ to the network.

TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?
Load balancers protect the system from DDoS attacks. The advantage of a jumpbox is to give access to a user that can be monitered.
Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.

TODO: What does Filebeat watch for? 
Any info that has been changed in the file 
TODO: What does Metricbeat record?
It records mettrics and statistics 
The configuration details of each machine may be found below.
Note: Use the Markdown Table Generator to add/remove values from the table.
| JumpBox  | Gateway | 10.0.02  | Linux Ubuntu 18.04 |
|----------|---------|----------|--------------------|
| Web1     | server  | 10.0.0.5 | Linux Ubuntu 18.04 |
| Web2     | Server  | 10.0.0.6 | Linux Ubuntu 18.04 |
| Web3     | Server  | 10.0.0.8 | Linux Ubuntu 18.04 |
| Elk      | Server  | 10.0.0.4 | Linux Ubuntu 18.04 |

Access Policies
The machines on the internal network are not exposed to the public Internet.
Only the _____ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

-42.112.164.50

Machines within the network can only be accessed by _____.

-Jumpbox Provisioner IP 10.0.0.2

A summary of the access policies in place can be found in the table below.

| Name        | Publicly Accessible  | Allowed IP's |
|-------------|----------------------|--------------|
| Jumpbox Pro | NO                   | 10.0.0.2     |
| Web1        | No                   | 10.0.0.5     |
| Web2        | No                   | 10.0.0.6     |
| Web3        | No                   | 10.0.0.8     |
| Elk         | No                   | 10.0.0.      |


Elk Configuration
Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...

TODO: What is the main advantage of automating configuration with Ansible?
Allows you to use multiple servers in a playbook
The playbook implements the following tasks:
-install docker.io, python-pip, docker container, launch docker container


The following screenshot displays the result of running docker ps after successfully configuring the ELK instance.

-182716.png

Target Machines & Beats
This ELK server is configured to monitor the following machines: 
TODO: List the IP addresses of the machines you are monitoring

-Web1 10.0.05, Web2 10.0.0.6
Web3 10.0.0.8

We have installed the following Beats on these machines:

TODO: Specify which Beats you successfully installed

These Beats allow us to collect the following information from each machine:

TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., Winlogbeat collects Windows logs, which we use to track user logon events, etc.

-Filebeat moniters and collects log files, events and specified locations while metricbeat collects metrics and statistics and sends them to a specified output.

Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:
SSH into the control node and follow the steps below:

Copy the _____ file to _____.
Update the _____ file to include...
Run the playbook, and navigate to ____ to check that the installation worked as expected.

TODO: Answer the following questions to fill in the blanks:

Which file is the playbook? Where do you copy it?

-/etc/ansible/file/filebeat.yml

Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?

_Which URL do you navigate to in order to check that the ELK server is running?
 
 -http://[your.ELK-VM.External.IP]:5601/app/kibana
