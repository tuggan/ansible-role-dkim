Role Name
=========

Deploy and configure [OpenDKIM](http://www.opendkim.org/)

Requirements
------------

After the role has completed you will have a folder named dkim (unless you changed `dkim_local_dir`) with one .txt file for each domain. You will have to add all domain entries contained within these files as DNS entries for your keys to be valid.

Role Variables
--------------

| Variable                | Required | Default                                         | Description                                 |
| ----------------------- | -------- | ----------------------------------------------- | ------------------------------------------- |
| dkim_domain             | Yes      |                                                 | Domain to setup DKIM for                    |
| dkim_selectors          | Yes      |                                                 | Selectors for the domain. Added to DNS      |
| dkim_trustedhosts       | No       |                                                 | OpenDKIM option                             |
| dkim_config_dir         | No       | /etc/opendkim                                   | Where the OpenDKIM config directory         |
| dkim_key_dir            | No       | {{ dkim_config_dir }}/keys                      | Where the OpenDKIM keyfiles and definitions |
| dkim_service_state      | No       | started                                         | State of the OpenDKIM systemd service       |
| dkim_service_enbled     | No       | true                                            | If the OpenDKIM service should be enabled   |
| dkim_config_template    | No       | opendkim.conf.j2                                | Specifies what template to use              |
| dkim_config_file        | No       | /etc/opendkim.conf                              | Path to the OpenDKIM configuration file     |
| dkim_keytable           | No       | {{ dkim_config_dir }}/KeyTable                  | OpenDKIM option                             |
| dkim_signingtable       | No       | {{ dkim_config_dir }}/SigningTable              | OpenDKIM option                             |
| dkim_externalignorelist | No       | {{ dkim_config_dir }}/TrustedHosts              | OpenDKIM option                             |
| dkim_internalhosts      | No       | {{ dkim_config_dir }}/TrustedHosts              | OpenDKIM option                             |
| dkim_trustedhosts_file  | No       | {{ dkim_config_dir }}/TrustedHosts              | Path to TrustedHosts file                   |
| dkim_mode               | No       | sv                                              | OpenDKIM option                             |
| dkim_subdomains         | No       | false                                           | OpenDKIM option                             |
| dkim_socket             | No       | local:/var/spool/postfix/opendkim/opendkim.sock | OpenDKIM option                             |
| dkim_requiresafekeys    | No       | false                                           | OpenDKIM option                             |
| dkim_local_dir          | No       | dkim                                            | Local folder where to place DKIM txt files  |
| dkim_socket_users       | No       | [postfix]                                       | List of users to add to the opendkim group  |


Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         tuggan.dkim
      vars:
        dkim_domain: domain.tld
        dkim_selectors:
          - homelab
        dkim_trustedhosts:
          - 10.0.0.10

License
-------

BSD
