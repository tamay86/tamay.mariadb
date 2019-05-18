Ansible Role: tamay.mariadb
=========

This role installs MariaDB from system repository.

Requirements
------------

None.

Role Variables
--------------

List of all variables, including default values.

    # Version of mariadb to be installed
    # 'default' will use the version in the default repository
    # Other versions will use the repository from mariadb.org
    # Possible values: 'default', '10.0', '10.1', '10.2', '10.3'
    mariadb_version: 'default'

Defines the version of MariaDB, that will be installed. Either use ```default``` for MariaDB packages from the system repository, or use a version number to install this version from the mariadb.org repository. 

    # Password of root user. Will be generated if left empty
    mariadb_root_password: ''

MariaDB password for root user. Ansible generate one, if this value is left empty.
    
    # List of databases to create
    mariadb_databases: []
    # Example:
    #mariadb_databases:
    #  - database1
    #  - database2

A list of databases that will be created.
    
    # List of users with privileges to create
    mariadb_database_users: []
    # Example:
    #mariadb_database_users:
    #  - name: user1
    #    password: test
    #    host: 192.168.1.5
    #    priv: '*.*:ALL,GRANT'

A list of users that will be created. **host**,**priv** and **password** are optional. 


Dependencies
------------

None.

Example Playbook
----------------

    ---
    
    - hosts: all
    
      vars:
        mariadb_root_password: 'tohQu5uloogee3Ch'
        mariadb_databases:
          - database1
          - database2
        mariadb_database_users:
          - name: user1
            password: ieChei1ieyieF2cu
            host: 192.168.1.5
            priv: '*.*:ALL,GRANT'
          - name: user2
            priv: 'database2.*:ALL'
          - name: user3
          - name: user4
    
      roles:
      - tamay.mariadb

License
-------

MIT

Author Information
------------------

tamay.mueller@gmail.com