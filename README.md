# FOSSA NOVA
Did your install of Ubuntu 20.04 Focal Fossa explode? Do the Fossa Nova!

## PURPOSE

This project is intended to provision an AFSAS developer's machine for development on all aspects of the AFSAS project.
If in the course of our project's lifecycle the techniques in this provisioner should become out-of-date or invalid, then it falls to you, dear reader, to take up the torch and update this project or burn it all down.

## USAGE

### Setup

If you're reading this on your own developer-workstation, then hopefully you have:

1. Imaged this machine with with your favorite OS
2. Performed basic machine set up tasks such as configuring your admin username

Assuming you have done these things and you have now acquired this provisioner, you should ensure that you have Ansible's basic dependencies met:

1. Ensure that you are connected to the internet.
2. Ensure that you have installed Ansible (you may uninstall it after, if you wish)

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

Run the Ansible Playbook named "playbook.yml"
- It is recommended that you run with some mode of "verbose" debugging (especially since this project is meant to run on localhost). Ansible has 4 levels of verboseness: "-v" up to "-vvvv"
- You will need to ask ansible to prompt you for your administrator password using "--ask-become-pass" to perform admin-level config changes.

``` bash
    ansible-playbook playbook.yml -vv --ask-become-pass
```

### Default behavior/settings

Default environment settings are defined in "/vars/defaults.yml":
- Environment variables are exported to the system in "/etc/profile".
- Tomcat server version 9.0.46 is installed in "/usr/local/tomcat/".

Default security settings are defined in "/vars/authentication.yml" (You will need to provide your own)
