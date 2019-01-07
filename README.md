# Search Guard Ansible role

This is based on the official Elasticsearch [Ansible role](https://github.com/elastic/ansible-elasticsearch) with a few modifications how plugins are handled. See [Example playbook](example_playbook)

```
cd example_playbook
vagrant up --no-provision
ansible-playbook -v -i inventory.yml site.yml
```

This repo is currently considered alpha quality, so do not use in production yet.

### Credits

* Robin Clarke, Jakob Reiter, Dale McDiarmid
* http://xplordat.com/2017/12/12/elk-stack-with-vagrant-and-ansible/

Licensed under ASLv2, originally developed by elastic.