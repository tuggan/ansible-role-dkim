Role Name
=========

Deploy and configure opendkim

Requirements
------------

None.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

    dkim_service_state
    dkim_service_enabled

Options for OpenDKIM service.

    dkim_config_dir
    dkim_key_dir

Options for where important folders are located. `dkim_config_dir` is the standard configuration directory. `dkim_key_dir` is where the keyfiles and definitions are located.

    dkim_config_template
    dkim_config_file

Options for configuration. `dkim_config_template` is specifies what template to use. `dkim_config_file` specifies where the OpenDKIM config file is located.

    dkim_keytable
    dkim_signingtable
    dkim_externalignorelist
    dkim_internalhosts
    dkim_trustedhosts_file

Options for where the different configuration files are located.

    dkim_mode
    dkim_subdomains
    dkim_socket
    dkim_requiresafekeys
    dkim_local_dir

Options for the OpenDKIM configuration.

    dkim_socket_users

Users to add to the OpenDKIM group.

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         tuggan.dkim

License
-------

BSD
