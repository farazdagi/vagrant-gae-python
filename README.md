Ubuntu 12.04 + Python 2.7 + Python SDK 1.8.9
==================

Vagrant box configuration for GAE's Python SDK. Provisioned using Ansible.

## Create VM
    vagrant up
    # Wait while machine is being created and provisioned..
    
## Start dev. application     
    vagrant ssh  # login into box 
    sudo dev_appserver.py --host 0.0.0.0 --admin_host 0.0.0.0 /project/helloworld --port 80
    
- Note 1: shared folder is /project
- Note 2: standard [helloworld application](https://developers.google.com/appengine/docs/python/gettingstartedpython27/helloworld) is used

## Accessing machine
    curl 10.1.0.30
    # or access this IP in your browser
  
- Note: it is advised that you add GAE's IP to your /etc/hosts, so that you can access it by more memorable name
