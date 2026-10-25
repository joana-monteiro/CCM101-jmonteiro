# Laboratory 09 — The Cloud Automation Engineer

## Mission Overview

Laboratory Activity 09 focuses on Linux automation using Bash scripting and Cron. I created sample application data, developed a backup script, and automated file compression into timestamped `.tar.gz` archives. I also explored scheduling daily backups at 2:00 AM to reduce manual work and improve data protection.

## Objectives

- Learn basic Bash scripting and variables.
- Create and manage application files and directories.
- Configure script execution permissions.
- Automate compressed backups using `tar`.
- Schedule recurring tasks using Cron.
- Verify backup archives and document results in GitHub.

## Tools and Technologies

- Ubuntu Linux
- Bash Scripting
- Nano Text Editor
- Cron Scheduler
- TAR and Gzip
- Markdown and GitHub

## Commands Executed

| Command | Purpose |
|---|---|
| `mkdir -p app-data` | Creates the application data directory. |
| `echo "This is critical client data." > app-data/data.txt` | Creates a sample data file. |
| `nano backup.sh` | Creates or edits the backup script. |
| `chmod +x backup.sh` | Makes the script executable. |
| `./backup.sh` | Runs the backup process manually. |
| `ls -lh backups/` | Lists generated archives and their sizes. |
| `tar -tzf backups/backup_YYYYMMDD_HHMMSS.tar.gz` | Checks the contents of a backup archive. |
| `env EDITOR=nano crontab -e` | Opens the Cron schedule editor. |
| `crontab -l` | Displays configured scheduled tasks. |

## Bash Backup Script

The `backup.sh` script compresses the application directory and saves it with a unique timestamp.

~~~bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

mkdir -p "$BACKUP_DIR"

tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" "$SOURCE_DIR"

echo "Backup completed at $TIMESTAMP!"
~~~

### Script Explanation

- **Variables:** Define the source and backup directories.
- **Timestamp:** Creates unique filenames for each backup.
- **Directory creation:** Ensures the destination folder exists.
- **Compression:** Packages application files into a `.tar.gz` archive.
- **Output messages:** Displays backup progress in the terminal.

## Cron Job Configuration

Cron automates tasks according to a specified schedule. The following entry runs the backup script daily at 2:00 AM.

~~~cron
0 2 * * * /root/backup.sh
~~~

| Field | Meaning |
|---|---|
| `0` | Minute 0 |
| `2` | Hour 2 AM |
| `*` | Every day of the month |
| `*` | Every month |
| `*` | Every day of the week |

To configure and verify the schedule, use:

~~~bash
env EDITOR=nano crontab -e
crontab -l
~~~

**Important:** Ensure the script uses the correct absolute paths when running through Cron. Relative paths may point to unexpected directories because Cron can use a different working directory.

## Backup Verification

Use the following commands to check the generated archives:

~~~bash
ls -lh backups/
tar -tzf backups/backup_YYYYMMDD_HHMMSS.tar.gz
~~~

The first command lists the backup files, while the second displays the archived contents. Replace the sample timestamp with the actual filename. Confirm that `data.txt` is included before considering the backup verified.

## Skills Learned

- Writing and executing Bash scripts.
- Managing Linux files and permissions.
- Compressing data using TAR and Gzip.
- Automating recurring tasks with Cron.
- Verifying backup archives.
- Documenting technical procedures using Markdown and GitHub.

## Conclusion

This activity provided hands-on experience in automating Linux backups using Bash and Cron. I learned how to create timestamped archives, configure scheduled tasks, and verify stored files. These skills are useful for cloud administration, system maintenance, and protecting important application data.

**Mission Completion:** The activity is complete when the backup script runs correctly, the archive contents are verified, the Cron schedule is configured, and the documentation is committed to the GitHub portfolio.
