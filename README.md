## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the _____ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly avaliable, in addition to restricting access to the network.

- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_
- The off-loading function of a load balancer defends an organization against distributed denial-of-service (DDoS) attacks. 
- A jump box is a secure computer that all admins first connect to before launching any administrative task or use as an origination point to connect to other servers or untrusted environments.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the jumpbox and system network.

- _TODO: What does Filebeat watch for?_

Filebeat is a lightweight shipper for forwarding and centralizing log data. - 

_TODO: What does Metricbeat record?_

Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specifyThe configuration details of each machine may be found below.

_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.1.0.4   | Linux            |
| TODO     | Web-1    | 10.1.0.5   | Linux            |
| TODO     | Web-2    | 10.1.0.6   | Linux            |
| TODO     | Elastic  | 10.2.0.4   | Linux            |

///////////////////////

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the elk server machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: Add whitelisted IP addresses_

-my macbook to through 5601
- jumpbook: ssh port 22 

Machines within the network can only be accessed by Jumpbox.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
my macbook with my ip

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 |40.77.89.74           |
| web 1 & 2| No                  |10.1.0.5 10.1.0.6     |
|RedTeamsLB|Yes - port 80        |                      |
| Elk      | Yes- HTTP and Kibana|10.0.0.0/16           |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_
* improve the scalability, consistency, and reliability and lastly reduces config error
The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install Docker
- Install Python3_pip
- Docker Module
- Increase memmory
- Download and Launch ELK Container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_
Web-1: 10.1.0.5
Web-2: 10.1.0.6

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_
* web 1 & 2 and ELK-Server
* filebeats and metricbeats

These Beats allow us to collect the following information from each machine:
Filebeats: Filebeat is a lightweight shipper for forwarding and centralizing log data. 
Metricbeats: collect metrics from the operating system and from services running on the server.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to http://[elk_server_ip]:5601/app/kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
* filebeat-config
* /etc/ansible/files/filebeat-config.yml to /etc/filebeat/filebeat.yml

- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_

* Update the config file
* install it on all server.

- _Which URL do you navigate to in order to check that the ELK server is running?
 * http://[ELK-server-IP]:5601/app/kibana.
 
 _As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._

* ansible-playbook
* ansible-playbook
