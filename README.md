# ansible-couchdb2-rpms

## Overview

It is an [Ansible](http://www.ansible.com/home) role to build RPMs (on CentOS 6.x) for SpiderMonkey and CouchDB 2.0.

### Why?
Docker is cool, but sometimes you need to deploy things the old-fashioned way.

## How to use
The playbook depends on the RVM role which you can get from Ansible Galaxy

`$ ansible-galaxy install rvm_io.rvm1-ruby`

I normally use a CentOS VM as an RPM build machine. Simply add this node to an Ansible inventory file, and then run:

`ansible-playbook -i inventory build.yaml` 

The role will build SpiderMonkey and CouchDB from source (compiled against Erlang 18 which is also automatically downloaded). 

It uses [FPM](https://github.com/jordansissel/fpm) to create the RPM files. 

Once the RPMS have been built, you can download them from http://[build-server-ip]/rpms (the Ansible role launches a web server automatically).

[TODO] Show how to deploy the RPM with Ansible.



