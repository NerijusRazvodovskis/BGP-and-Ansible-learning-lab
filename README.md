# BGP and Ansible learning lab

This repository provides a pre-configured [Containerlab](https://containerlab.dev/) topology featuring 8 virtual machines running [Ubuntu Generic VM](https://containerlab.dev/manual/kinds/generic_vm/). The environment is designed to facilitate BGP (Border Gateway Protocol) studies and is configured to install [FRR](https://docs.frrouting.org/en/latest/) using [Ansible](https://docs.ansible.com/) for streamlined setup and automation.

## Key Features

* Seamless BGP Practice: A robust, quickly deployable setup to dive into BGP routing, peering configurations, and advanced BGP topics.
* Flexible Environment: Modify and expand the topology as needed to test complex network scenarios.
* Ansible Integration: Enhance your Ansible skills by automating network configurations and managing routing changes, providing dual-purpose learning in both network engineering and automation.

## Why Use This Topology?

This setup is perfect for network engineers and enthusiasts who want to build their expertise in BGP without the hassle of manual configuration. The integration of Ansible makes it ideal for training in network automation, enabling you to script configurations, automate installations, and maintain network consistency.

## Lab Topology
![image](https://github.com/user-attachments/assets/ec56b7d8-2ee4-46bb-9e9b-c40958216394)

After deploying the lab and running the ansible, all of the BGP sessions will be UP already.

## Requirements

* [Install](https://containerlab.dev/install/) the Containerlab.
* Any of the Ansible version should be fine, i'm using one from: `pip install -r ./requirements.txt`.

## Starting the lab

* Execute `./deploy-lab.sh`.
* Run the ansible for init configuration with `ansible-playbook playbooks/configure.yml -i clab-bgp-learning/ansible-inventory.yml`.

## Destroying the lab

* Execute `./destroy-lab.sh`.

## Reaching the nodes

After you bring up the lab UP, following entries will be generated to `/etc/hosts`:

```
###### CLAB-bgp-learning-START ######
172.20.20.8	isp3
172.20.20.6	isp4
172.20.20.5	isp5
172.20.20.9	isp6
172.20.20.4	customer1
172.20.20.7	customer2
172.20.20.3	isp1
172.20.20.2	isp2
```

You can reach any of them by executing `ssh clab@isp1`, password `clab@123`.
