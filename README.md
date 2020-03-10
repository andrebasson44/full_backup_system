# full_backup_system

AUTHOR:       Andre Basson

DESCRIPTION:  Typical FULL (image) backup script, which syncs data - files and directories listed in ./toBackup.txt - either between a 
              remote and local host, local to local host, or local to remote host.  ONLY in the first scenario data is PULLed from the 
              remote host (as opposed to the remote host instigating the transfer by PUSHing the data).  The other two scenarios PUSHes     
              data.

INSTRUCTIONS
  1. create a directory to house all files, eg. ~/full-backup
  2. copy all files into directory in (1)
  3. list all the directories (or files) to backup in ./toBackup.txt
  4. configure backup parameters in ./full-backup.conf  (follow comments for guidance)
  5. optional: add files/directories to exclude from backup in ./backup_exclude_list.txt
  6. optional: automate backups with crontab
  7. ensure all requirements (see below) has been fulfilled.
  8. run the *.sh file either manually or via crontab scheduled task

REQUIREMENTS:	
  1. System software:
    a) *OPTIONAL:  A local, send-only SMTP server (e.g. Postfix) - no dedicated email or 3rd party SMTP server is required
  					Postfix configured to forward all system-generated email sent to root, to skyqode@gmail.com  	
  					(see documentation or https://www.digitalocean.com/community/tutorials/how-to-install-and-configure-postfix-as-a-send-only-smtp-server-on-ubuntu-14-04)
    b) Rsync
  	c) SSH - with hosts configured for RSA public/private key pair
  
  2. User software:
    a) Program path - if not in system path already - should be listed (see RESOURCE FILES section)
