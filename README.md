Role Name
=========

ansible role for installing and configuring the tivoli backup client

Requirements
------------

A backup client must be requested from the ITA of the Uib.
You will get the Server IP, the backup client name and a password from there.

After the initial installation on a new system, the dsmc command must be executed once and the password entered. The binary file /etc/adsm/TSM.PWD created must be inserted into the role into  files/TSM.PWD.ansible_hostname.
It will be used in further installations.


Role Variables
--------------

All variables are defined in the defaults/main.yml file. 
You need to set the backupclient_name and the directories you want to backup.
backupserver_ip usually does not need to be changed.



Dependencies
------------


Example Playbook
----------------

    - hosts:
        - db.usegalaxy.no
      vars:
        backupdirs: "/etc /var/spool/cron"
        backupclient_name: apo.ii
        backupserver_ip: 129.177.30.195
      become: true
      roles:
        - DBUSEGALAXYNO
      tags: tivoli


License
-------

BSD

Author Information
------------------

Elixir Norway/Bergen University
