# Ansible script for setting up a Wordpress server on CentOS 7

### How to:
1. Edit the `inventory` file so that it contains ip address (and possibly password) of your machine's root account.
2. Run the script with `$ ansible-playbook -i inventory site.yaml`.


#### Note
If you don't want to specify the password in a script files, run the script with `--ask-pass` option and you will be prompted to type your password.
If you access to a host via ssh for the first time, you will be asked about whether to add RSA key fingerprint of this host.
However, with ask-pass being specified, ansible will directly run into an error if this is the first time you access to that host.
To walk through this, simply run `$ export ANSIBLE_HOST_KEY_CHECKING=False` in terminal or create a file `~/.ansible.cfg` with following content:
```
[defaults]
host_key_checking = False
```

#### Directory structure:
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
