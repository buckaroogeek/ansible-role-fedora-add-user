Role Name
=========

Wrapper around ansible.builtin user to add a user account to virtual or physical Fedora machine. Enables root level access with passwordless sudo by default. Configures remote machine with account for user running ansible by default.

Requirements
------------

Assumes host machine is linux with ssh keys in the well known location for user accounts. Also assumes sudo is configured to read /etc/sudoers.d/ directory for additional configuration files.

Role Variables
--------------

End user configurable variables are listed below, along with default values (see `defaults/main.yaml`):

| Variable   | Default Value | Notes |
| ---------- | ------------- | ----- |
| ua_wheel | true | When true, adds user to wheel group |
| ua__pub_key | id_ed25519.pub | name of public ssh key to add |
| ua_userid | current user    | Id to create on remote machine. Defaults to current user. |
| ua_sudoer | true    | Add sudoer file for passwordless sudo access. |

Dependencies
------------

ansible.posix collection

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: fedora_user_add }

License
-------

BSD

Author Information
------------------

Brad Smith
bradley.g.smith@gmail.com
