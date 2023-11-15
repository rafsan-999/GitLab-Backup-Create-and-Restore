# GitLab-Backup-and-Restore
video link: https://www.youtube.com/watch?v=gSTWflp3jYc

# GitLab info
    gitlab-rake gitlab:env:info
# Manual backup create command
    gitlab-rake gitlab:backup:create
# Default location where gitlab backup restored
    /var/opt/gitlab/backups
# Before restore backup must stop these services
    gitlab-ctl stop unicorn
    gitlab-ctl stop sidekiq
    gitlab-ctl stop puma
    gitlab-ctl status
# Restore backup
Backup file should look like these: <1699940401_2023_11_14_16.3.4_gitlab_backup> ignore <_gitlab_backup> just copy <1699940401_2023_11_14_16.3.4>

    gitlab-rake gitlab:backup:restore BACKUP = 1699940401_2023_11_14_16.3.4 
# After Successfully restore backup run the following command below
    gitlab-ctl reconfigure 
    gitlab-ctl restart
