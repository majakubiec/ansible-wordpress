# Ansible script for setting up a Wordpress server on CentOS 7

Before you start the script, remember to edit the `inventory` file so that it contains ip address and credentials of your machine.

Run it with `$ ansible-playbook -i inventory site.yaml`.



```
├── inventory
├── roles
│   ├── apache
│   │   ├── handlers
│   │   │   └── main.yml
│   │   └── tasks
│   │       └── main.yml
│   ├── common
│   │   ├── tasks
│   │   │   └── main.yml
│   │   └── vars
│   │       └── main.yml
│   ├── mysql
│   │   └── tasks
│   │       └── main.yml
│   ├── php
│   │   └── tasks
│   │       └── main.yml
│   └── wordpress
│       ├── tasks
│       │   └── main.yml
│       ├── templates
│       │   └── wp-config.php
│       └── vars
│           └── main.yml
└── site.yaml
```
