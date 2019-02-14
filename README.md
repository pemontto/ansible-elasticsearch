# Search Guard Ansible role

This role is based on the official Elasticsearch [Ansible role](https://github.com/elastic/ansible-elasticsearch) with a few modifications how plugins are handled. 

## Limitations

* This role does not install Kibana currently. Only an Elasticsearch cluster with the Search Guard plugin will be provisioned at the moment.
* Role is shipped with default demo certificates. Do NOT use them in production.
* No Kitchen tests for Search Guard yet

## Usage

* You do not need the official Elasticsearch Ansible role alongside with this role.

```
ansible-galaxy install floragunncom.search_guard_ansible
```
Then create a playbook like shown in the [Example playbook](example_playbook)

### inventory.yml

Define your hosts of which the elasticsearch cluster is composed of and which node type (master, data, client) you would
like to run on which host. Also assign the maximum heap here.

### group_vars/all.yml

Adjust the Elasticsearch and Search Guard version as well as the elasticsearch.yml.

### site.yml

The entrypoint for your playbook. This is mainly executing the floragunncom.search_guard_ansible role and the sgadmin handler afterwards
to initialize Search Guard.

## Running the example playbook with vagrant

```
git clone https://github.com/floragunncom/search-guard-ansible.git
cd search-guard-ansible/example_playbook
vagrant up --no-provision
ansible-playbook -v -i inventory.yml site.yml
```

This repo is currently considered alpha quality, so do not use in production yet.

### Credits

* Robin Clarke, Jakob Reiter, Dale McDiarmid
* http://xplordat.com/2017/12/12/elk-stack-with-vagrant-and-ansible/

Licensed under ASLv2, originally developed by elastic.