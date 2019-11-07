Rsync backup
============

This role creates a simple backup script to a rsync server

Role Variables
--------------

Several variables can be set up.

Information about the server :
  rsyncbackup_server: the remote rsync server to use
  rsyncbackup_remotefolder: the name of the rsync folder

Information local to the computer being backed up :
  rsyncbackup_localuser: the local user used to run the backup script
  rsyncbackup_hour: hour for the cron job to run the backup script
  rsyncbackup_min: minute for the cron job to run the backup script
  rsyncbackup_conf: configuration file where files or folder to backup are added (one per line)

Example Playbook
----------------

Example :

    ---
    - hosts: servers
      roles:
        - role: thomfab.ansible-byobu
          rsyncbackup_server: "myrsyncserver"
          rsyncbackup_remotefolder: "backup"
          rsyncbackup_localuser: "root"
          rsyncbackup_hour: 10
          rsyncbackup_min: 0
          rsyncbackup_conf: "/etc/backup.conf"


License
-------

BSD
