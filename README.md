gudron.sudo
=========

Role for install sudo package and manage sudo privelegies

Role Variables
--------------

### General variables
  * `sudoers_params: dict`
    Dict with main parameters of sudoers file. Like `path`, `secure_path` and etc.
    
  * `users_list_params: list` 
    List of sudo users parameters

    * `name: string`
      User name

    * `no_pwd_sudo: boolean`
      Flag of disabling promt password on using sudo command

  * `groups_list_params: list` 
    List of sudo groups parameters 
    
    * `name: string`
      User name

    * `no_pwd_sudo: boolean`
      Flag of disabling promt password on using sudo command

    Full example: [defaults/main.yml](defaults/main.yml).

Example Playbook
----------------

    - hosts: example_project:&example_project_stage
      any_errors_fatal: "{{ any_errors_fatal | default(true) }}"
      gather_facts: True

      roles:
        - name: gudron.sudo
          vars: 
            users_list_params:
              - name: ansible_example
                no_pwd_sudo: False
            groups_list_params:
              - name: wheel
                no_pwd_sudo: True

License
-------

Apache 2.0
