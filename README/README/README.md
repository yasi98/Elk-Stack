## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __playbook___ file may be used to install only certain pieces of it, such as Filebeat.

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

Load balancing ensures that the application will be highly __efficient__, in addition to restricting __connections___ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __log files___ and system __metrics___.
- _TODO: What does Filebeat watch for?_ log files
- _TODO: What does Metricbeat record?_ it records metrics from the operating system and from services running on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.7   | Linux            |
| ELK     |elk server |  10.1.0.4 |  Linux            |
| web-1     |  web server| 10.0.0.11  |  Linux        |
| web-2     |  web server  |10.0.0.6   |  Linux       |
| web-3    |  web server  |  10.0.0.10  |    Linux    |


### Access Policies

The machines on the internal network are not exposed to the public Internet.

Only the __jumpbox___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 144.91.179.186

Machines within the network can only be accessed by __jumbpox vm___.
- jumpbox, 10.0.0.7 52.183.113.85

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 144.91.179.186       |
| elk      | yes                 | 10.0.0.7 52.183.113.85 |
| web servers    | No  | 10.0.0.7 52.183.113.85         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- faster than installing manually

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- install docker.io
- install python3-pip
- install docker python module
- increase memory
- download elk container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

(Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.11
- 10.0.0.6
- 10.0.0.10

We have installed the following Beats on these machines:
- Filebeat and Metricbeat installed on elk and web server VMs.

These Beats allow us to collect the following information from each machine:
- Filebeat collects data about file system. Metricbeat collects machine metrics, such as uptime.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned:

SSH into the control node and follow the steps below:
- Copy the __playbook___ file to _____.
- Update the __hosts___ file to include ip address of elk vm.
- Run the playbook, and navigate to http://52.234.132.156:5601/app/kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
