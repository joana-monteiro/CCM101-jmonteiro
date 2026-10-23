# Checkpoint 6 — Backup Script Technical Documentation

## 1. Overview

This documentation describes the backup automation process performed during Laboratory Activity 9: The Cloud Automation Engineer. The activity covers developing a Bash script, setting file execution permissions, generating compressed backup archives, and configuring Cron to execute the script automatically.

The main objective is to minimize repetitive manual tasks, maintain organized backup files, and demonstrate the practical use of Linux commands in cloud administration.

## 2. Complete Bash Backup Script

The following code presents the `backup.sh` script implemented during the laboratory activity.

### Script Code

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

### Explanation of the Script Components

| Component | Description and Function |
|---|---|
| `#!/bin/bash` | Identifies Bash as the interpreter responsible for running the script. |
| `SOURCE_DIR="app-data"` | Stores the path of the directory containing the application files. |
| `BACKUP_DIR="backups"` | Specifies the destination directory for the backup archives. |
| `TIMESTAMP=$(date +"%Y%m%d_%H%M%S")` | Retrieves the current date and time to generate a distinct name for each backup file. |
| `echo` | Prints informational messages to the terminal. |
| `mkdir -p "$BACKUP_DIR"` | Creates the backup destination directory when it does not exist. |
| `tar -czf` | Packages and compresses the source directory into a gzip-compressed archive. |

## 3. Commands Executed During the Laboratory

This section describes the commands used in the previous checkpoints to prepare sample application data, develop and execute the backup script, and establish an automated backup schedule.

### A. Create the Application Data Directory

```bash
mkdir -p app-data
```

**Purpose:** Creates the `app-data` directory, which serves as the location for the files included in the backup.

- `mkdir` — Creates a new directory.
- `-p` — Creates missing parent directories when necessary and avoids errors when the target directory already exists.

### B. Generate a Sample Data File

```bash
echo "This is sample application data." > app-data/data.txt
```

**Purpose:** Creates a text file named `data.txt` inside the `app-data` directory and writes sample application data into it.

- `echo` — Outputs the specified text.
- `>` — Redirects the output to a file, creating the file if necessary or overwriting its existing contents.
- `app-data/data.txt` — Defines the destination path of the text file.

### C. Create or Modify the Backup Script

```bash
nano backup.sh
```

**Purpose:** Launches the Nano text editor, allowing the user to create or update the contents of `backup.sh`.

After inserting the Bash commands, save the changes and close the editor.

### D. Enable Script Execution

```bash
chmod +x backup.sh
```

**Purpose:** Grants execute permission to the backup script so it can be launched directly from the terminal.

### E. Execute the Backup Script

```bash
./backup.sh
```

**Purpose:** Runs the script located in the current directory. It attempts to compress the contents of `app-data` and place the resulting archive in the `backups` directory.

### F. Examine the Generated Backup Files

```bash
ls -lh backups/
```

**Purpose:** Lists the files stored in the backup directory and displays their sizes in a readable format.

- `ls` — Displays the contents of a directory.
- `-l` — Shows detailed file information, including permissions, ownership, and file size.
- `-h` — Displays file sizes using readable units, such as KB, MB, or GB.

### G. Edit the Cron Configuration

```bash
env EDITOR=nano crontab -e
```

**Purpose:** Opens the current user's Cron configuration using the Nano editor, enabling the user to create or modify scheduled commands.

To run the backup script every day at 2:00 AM, add the following entry:

```cron
0 2 * * * /root/backup.sh
```

Save the configuration and exit the editor to apply the schedule.

### H. Confirm the Cron Configuration

```bash
crontab -l
```

**Purpose:** Displays the scheduled tasks configured for the current user. Verify that the backup command appears in the list.

## 4. File Permissions and the `chmod +x` Command

Linux file permissions control whether users are allowed to read, write, or execute files. These permissions help manage access to scripts and other system resources.

The command below adds execution permission to the backup script:

```bash
chmod +x backup.sh
```

The command consists of the following parts:

| Component | Explanation |
|---|---|
| `chmod` | Modifies the permission settings of a file or directory. |
| `+x` | Adds execute permission to the specified file. |
| `backup.sh` | Identifies the script whose permissions will be updated. |

To inspect the permissions assigned to the script, execute:

```bash
ls -l backup.sh
```

The resulting output displays the file's permission information. The letter `x` indicates that execute permission is enabled for the corresponding user, group, or other users.

## 5. Cron Job Configuration

Cron is a Linux scheduling utility that automatically executes commands and scripts at predefined times. It allows system administrators to perform recurring maintenance tasks without manually starting each operation.

### Cron Schedule

```cron
0 2 * * * /root/backup.sh
```

This configuration instructs Cron to execute the backup script daily at 2:00 AM, based on the system's local time.

### Explanation of the Schedule Fields

| Field | Value | Description |
|---|---|---|
| Minute | `0` | Executes the task at the beginning of the hour. |
| Hour | `2` | Specifies 2:00 AM. |
| Day of Month | `*` | Applies to every day of the month. |
| Month | `*` | Applies to every month. |
| Day of Week | `*` | Applies to every day of the week. |

### Important Scheduling Considerations

The backup script references the `app-data` and `backups` directories using relative paths, while the Cron configuration specifies the absolute path `/root/backup.sh`. Because Cron may execute commands from a different working directory, these relative paths might not point to the intended directories.

To prevent this problem,
