Role Name
=========

Wrapper around ansible.builtin user to add a user account to virtual or 
physical Fedora machine. Enables root level access with passwordless root 
access via sudo if toggled.

Requirements
------------

Assumes host machine is linux with ssh keys in the well known location for 
user accounts. Also assumes sudo is configured to read sudoers.d/  
directory for additional configuration files.

Role Variables
--------------

End user configurable variables are listed below, along with default values (see `def
aults/main.yaml`):

| Variable   | Default Value | Notes |
| ---------- | ------------- | ----- |
| ua_wheel | true | When true, adds user to wheel group |
| ua__pub_key | id_ed25519.pub | name of public ssh key to add |
| ua_userid | current user    | Id to create on remote machine. Defaults to current user. |
| ua_sudoer | true    | Add sudoer file for passwordless sudo access. |

The variable below is defined in `./vars/main.yaml` and not intended for modification
 at runtime.
| Variable   | Default Value | Notes |
| ---------- | ------------- | ----- |
| dlp_packages | python3-dnf-plugin-local<br>createrepo_c | The packages installed by
 the role |


Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
