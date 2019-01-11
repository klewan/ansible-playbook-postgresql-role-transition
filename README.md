Ansible Playbook: postgresql-role-transition
============================================

Perform PostgreSQL server role transition (switchover/failover)

Supported OS:
-------------
* RedHat
* CentOS
* OracleLinux

Requirements
------------

This playbook requires the postgresql-role-transition and postgresql-instance roles.

`$ ansible-galaxy install -r roles/requirements.yml`

Examples
--------

    $ ansible-playbook playbook.yml --list-tasks
    $ ansible-playbook playbook.yml --list-tags

Perform PostgreSQL server role transition

    $ ansible-playbook playbook.yml

Execute tasks for a primary server only

    $ ansible-playbook playbook.yml --tags=postgresql_role_transition_process_primary
	
Execute tasks for a standby server only

    $ ansible-playbook playbook.yml --tags=postgresql_role_transition_process_standby
	
Promote a standby to be a new primary server

    $ ansible-playbook playbook.yml --tags=postgresql_role_transition_promote_standby

Create replication slots

    $ ansible-playbook playbook.yml --tags=postgresql_role_transition_create_replication_slots

Synchronize a PGDATA data directory with primary data directory (pg_rewind)

    $ ansible-playbook playbook.yml --tags=postgresql_role_transition_standby_synchronize_server

Set up config files

    $ ansible-playbook playbook.yml --tags=postgresql_role_transition_standby_config_files

	
License
-------

GPLv3 - GNU General Public License v3.0

Author Information
------------------

This playbook was created in 2018 by [Krzysztof Lewandowski](mailto:Krzysztof.Lewandowski@fastmail.fm).


