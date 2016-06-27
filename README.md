ansible-aws-rds
=========

Creates RDS instances.

Requirements
------------

boto


Role Variables
--------------

Role accepts list of servers to create. Each list is a dictionary with required parameters.

Dependencies
------------

none

Example Playbook
----------------

    - hosts: databases
      vars:
      aws_rds                 :
        - security_group_id   : "sg-3a27b45z"
          publicly_accessible : False
          db_engine           : "postgres"
          db_name             : "testdb"
          instance_name       : "testremoveme"
          engine_version      : "9.4.5"
          size                : "20"
          instance_type       : "db.t2.micro"
          wait                : true
          wait_timeout        : 600
          command             : "create"
          username            : "abcdefg"
          password            : "abcdefg123"

      roles:
         - { role: ansible-aws-rds }
