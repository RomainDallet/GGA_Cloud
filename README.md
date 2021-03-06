# About the project

The Galaxy Genome Annotation (GGA) (https://galaxy-genome-annotation.github.io) project consists of several projects and tool suites that are working closely together to deliver a comprehensive, scalable and easy to use Genome Annotation experience. The Galaxy Genome annotation environment not only offers a wide array of high-profile tools in Galaxy for structural and functional annotation, but also a highly integrated set of “dockerized” GMOD tools, a collection of open-source applications for visualizing, annotating, and managing genomic data (JBrowse, Apollo, Tripal, Chado). Galaxy is used as a data loading orchestrator for administrators, with dedicated Galaxy tools and workflows to interact with GMOD tools, and Python libraries to make all tools work together.

The EOSC-Life project aims to create an open collaborative digital space for life science in the European Open Science Cloud (EOSC). As part of the EOSC-Life WP2, dedicated to make computational tools, workflows and registries FAIR, we planned to provide the GGA environment available in the cloud. So we are currently developing Ansible recipes deploy the GGA environment in an Openstack cloud infrastructure. These Ansible recipes allow the deployment of a Virtual Machine in a cloud via the Terraform software, the installation of the GGA environment and its dependencies, as well as loading data into the Galaxy library.

# Ansible

## Inventory

`development/hosts`

## Use

### Dependencies installation

```
ansible-galaxy install -r requirements.yml 
```
or to install both separately :
```
ansible-galaxy install role -r requirements.yml 
ansible-galaxy install collection -r requirements.yml 
```

Need to add `collections_paths = ./collections` in ansible.cfg to use collections.

### Run playbooks
#### Dry mode

```
ansible-playbook playbook_terraform.yml --check
ansible-playbook playbook_gga_genocloud.yml --check
```

#### Real mode

```
ansible-playbook playbook_terraform.yml
ansible-playbook playbook_gga_genocloud.yml
```

![cloud_scheme](https://github.com/abims-sbr/GGA_Cloud/blob/master/static/images/cloud_scheme.png)
