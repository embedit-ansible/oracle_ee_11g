Oracle EE 11g
=============

Simplifyed Oracle 11g EE install role

Role Variables
--------------

| Var Name                   | Required | Default      | Description |
| -------------------------- | :------: | ------------ | ----------- |
| `oracle_all_password`      | yes      | | Oracle Database password |
| `oracle_clean_install`     | no       |              | Define if you want to clean install |
| `oracle_hostname`          | no       |              | oracle.example.com |
| `oracle_install_files_dir` | no       | ../Downloads | Folder containg install files  `linux.x64_11gR2_database_1of2.zip` and `linux.x64_11gR2_database_2of2.zip` |

Dependencies
------------

- https://galaxy.ansible.com/embedit-ansible/oracle-tools-create_restore_point/

Example Playbook
----------------

    - hosts: all
      become: true
      vars:
        oracle_hostname: oracle.example.com
        oracle_install_files_dir: ../Downloads
        restore_point_name: fresh_install
      vars_prompt:
        - name: "oracle_all_password"
          prompt: "Oracle Password"
          private: yes
      roles:
        - role: ansible-role-oracle-ee-11g

License
-------

MIT

Author Information
------------------

Mario Vejlupek
