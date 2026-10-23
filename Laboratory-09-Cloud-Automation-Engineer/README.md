# Laboratory 09 — The Cloud Automation Engineer

## Mission Overview

Laboratory Activity 9 focuses on Linux automation through Bash scripting and Cron scheduling. During this activity, I created a sample application directory, prepared a data file, and developed a Bash script to automate the backup procedure.

The script creates a timestamp-based filename and compresses the contents of the `app-data` directory into a `.tar.gz` archive saved in the `backups` directory. I also configured the script's execution permissions and explored how Cron can schedule the backup process to run automatically every day at 2:00 AM.

This activity demonstrates how automation can minimize repetitive manual work, increase operational efficiency, and maintain an organized backup system.

## Objectives

- Understand the fundamentals of Bash scripting, including variables, comments, and the shebang.
- Create directories and prepare sample application data.
- Write and modify Bash scripts using the Nano text editor.
- Configure script execution permissions using `chmod +x`.
- Compress application files into timestamped `.tar.gz` backup archives.
- Set up and verify recurring tasks using Cron.
- Inspect generated backup files and verify archive contents.
- Document the implementation process and results using Markdown.
- Add the completed laboratory activity to the GitHub Cloud Computing Portfolio.

## Commands Executed

The following commands were used to prepare application data, develop and execute the backup script, examine the resulting archives, and configure the scheduled task.

| Command | Purpose |
|---|---|
| `mkdir -p app-data` | Creates the directory used to store sample application data. |
| `echo "This is critical client data." > app-data/data.txt` | Creates `data.txt` and saves sample text in the file. |
| `nano backup.sh` | Opens the Nano editor to create or modify the backup script. |
| `chmod +x backup.sh` | Assigns execute permission to the Bash script. |
| `./backup.sh` | Executes the backup script from the current directory. |
| `ls -lh backups/` | Displays the backup files along with their sizes in a readable format. |
| `tar -tzf backups/backup_YYYYMMDD_HHMMSS.tar.gz` | Displays the contents of a compressed archive using its actual filename. |
| `crontab -l` | Shows the scheduled Cron jobs configured for the current user. |
| `env EDITOR=nano crontab -e` | Opens the user's Cron configuration in Nano for editing. |

## Bash Backup Script

The `backup.sh` file contains the commands needed to automate the creation of a compressed backup of the application data.

```bash
#!/bin/bash
# Automated Backup Script for CloudNova Technologies

SOURCE_DIR="app-data"
BACKUP_DIR="backups"
TIMESTAMP=$(date +"%Y%m%d_%H%M%S")

echo "Initiating automated backup..."

# Create the backup directory if it does not exist
mkdir -p "$BACKUP_DIR"

# Compress the source directory into a tarball (.tar.gz)
tar -czf "$BACKUP_DIR/backup_$TIMESTAMP.tar.gz" "$SOURCE_DIR"

echo "Backup completed successfully at $TIMESTAMP!"
```

### Explanation of the Script

1. **Directory variables:** `SOURCE_DIR` specifies the location of the application data, while `BACKUP_DIR` defines the destination for the backup archives.
2. **Timestamp generation:** The `date` command produces a date-and-time identifier that gives each backup a distinct filename.
3. **Directory creation:** The `mkdir -p` command ensures that the backup destination exists before the archive is created.
4. **Data compression:** The `tar -czf` command packages and compresses the source directory into a `.tar.gz` file.
5. **Terminal messages:** The `echo` commands display progress information to indicate the start and completion messages of the backup process.

**Note:** The final terminal message does not automatically guarantee that the backup was successful. The generated archive should be checked to confirm that it exists and contains the expected files.

## Cron Job Configuration

Cron is a Linux utility that executes commands or scripts automatically according to a defined schedule. It is useful for managing recurring administrative tasks without requiring manual execution each time.

The following entry schedules the backup script to run daily at 2:00 AM:

```cron
0 2 * * * /root/backup.sh
```

### Cron Schedule Breakdown

| Field | Value | Explanation |
|---|---|---|
| Minute | `0` | Executes the task at the beginning of the hour. |
| Hour | `2` | Specifies 2:00 AM. |
| Day of Month | `*` | Runs on every day of the month. |
| Month | `*` | Runs during every month. |
| Day of Week | `*` | Applies to every day of the week. |

### Steps to Configure Cron

1. Open the Cron configuration editor:

   ```bash
   env EDITOR=nano crontab -e
   ```

2. Insert the following scheduling entry:

   ```cron
   0 2 * * * /root/backup.sh
   ```

3. Save the configuration and close the Nano editor.
4. Confirm that the schedule has been registered:

   ```bash
   crontab -l
   ```

**Important:** Ensure that `/root/backup.sh` points to the actual location of the script. Since the script uses relative paths for `app-data` and `backups`, it may access the wrong directories when executed by Cron. Using absolute paths or explicitly changing to the correct working directory helps ensure that the script reads the intended source files and saves the archives to the correct destination.

## Backup Verification

After executing the script, inspect the output to determine whether the backup archive was generated and whether it contains the expected data.

### List the Generated Backup Files

```bash
ls -lh backups/
```

This command lists the files in the backup directory and displays details such as file sizes and permissions in a human-readable format.

### Inspect the Archive Contents

```bash
tar -tzf backups/backup_YYYYMMDD_HHMMSS.tar.gz
```

Replace `YYYYMMDD_HHMMSS` with the timestamp included in the actual backup filename.

When the correct archive is specified, the command should display its contents, including the `app-data` directory and the `data.txt` file.

The command options serve the following purposes:

- `-t` — Lists the files contained in the archive.
- `-z` — Handles gzip-compressed data.
- `-f` — Specifies the archive file to access.

## Skills Learned

Through this laboratory activity, I gained practical experience in the following areas:

- **Bash Scripting:** Developing scripts to automate repetitive administrative tasks.
- **Linux File Management:** Creating directories and organizing application files.
- **File Permissions:** Applying execution permissions through the `chmod +x` command.
- **Data Compression:** Using `tar` and gzip to package files into compressed archives.
- **Timestamp-Based Backups:** Generating uniquely named backup files based on the date and time.
- **Cron Scheduling:** Automating recurring tasks according to a predefined schedule.
- **Backup Verification:** Checking generated archives and examining their contents.
- **Technical Documentation:** Recording procedures, commands, and results in Markdown.
- **GitHub Version Control:** Organizing and maintaining laboratory documentation in a cloud computing portfolio.

## Conclusion

Laboratory Activity 9 provided practical experience in using Bash scripting and Cron to automate the backup process in a Linux environment. By preparing application data, creating a backup script, configuring file permissions, compressing files, and establishing a recurring schedule, I gained a better understanding of how automation supports efficient system administration.

I also learned that reliable automation involves more than simply writing and running commands. Testing scripts, verifying backup archives, reviewing Cron configurations, and documenting the process are necessary to maintain dependable operations and protect important data.

The knowledge and skills acquired through this activity will support my future IT projects, particularly those involving cloud administration, task automation, system maintenance, and data management.
