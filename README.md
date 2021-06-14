# FOSSA NOVA
J Carr, 7/14/2021

## PURPOSE

This project is intended to provision an AFSAS developer's machine for development on all aspects of the AFSAS project.
If in the course of our project's lifecycle the techniques in this provisioner should become out-of-date or invalid, then it falls to you, dear reader, to take up the torch and update this project or burn it all down.

## USAGE

### Setup

If you're reading this on your own developer-workstation, then hopefully you have:

1. Imaged this machine with with your favorite OS
2. Performed basic machine set up tasks such as configuring your admin username, setting up your favorite dot file configs

Assuming you have done these things and you have now been handed this provisioner, you should ensure that you have Ansible's basic dependencies met:

1. Ensure that you are connected to the internet.
2. Ensure that you have installed Python 2.6 or greater (on Ubuntu, it's included by default)

    ``` bash
    # Is Python installed?
    which python

    # Which version?
    python --version
    ```

3. Ensure that you have installed Ansible (you may uninstall it after, if you wish)

    ``` bash
    # Is Ansible installed?
    which ansible

    # Probably not
    sudo apt-get update
    sudo apt-get install software-properties-common
    sudo apt-add-repository ppa:ansible/ansible
    sudo apt-get update
    sudo apt-get install ansible
    ```

### Run

Run the Ansible Playbook named "playbook.yml" in your choice of verbose mode (in the example below we're using more-verbose) so we can see what's going on and ask for the admin password when admin rights are required:

``` bash
    ansible-playbook playbook.yml -vv --ask-become-pass
```

### Default behavior/settings

This provisioner's default settings are defined in "/vars/defaults.yml"

- Environment variables are exported to the system in "/etc/profile".
- Tomcat server version 8.5.11 is installed in "/usr/local/tomcat/".

