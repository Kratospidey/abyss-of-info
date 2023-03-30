---
{"dg-publish":true,"permalink":"/itl-project/"}
---

# Automatic Backup System

> [!info] Group Members 
> F004 Param Makwana
> F010 Jash Kanani
> F011 Yash Kalbhor
> F018 Aditya Sharma

# Aim
To create an automatic backup system using bash script

# Abstract
The Automatic Backup System is designed to provide an automated and efficient backup solution for Linux users. The project uses Bash scripting language to compress the user-specified files and directories into a zip file and then uploads it to a remote destination using rclone. The script checks the existence of required dependencies, including zip and rclone, and ensures that rclone is configured before proceeding with the backup process.

The system aims to provide a hassle-free and simple solution for users to backup their important data to a secure remote location, such as Google Drive, ensuring that their data remains safe and easily recoverable in the event of data loss or system failure. The Automatic Backup System is a reliable and efficient way to backup user data and provide peace of mind to users about their important files and data.
# Theory
The Automatic Backup System is a backup solution for Linux users that is designed to automate the backup process for important files and directories. The project uses Bash scripting language to create a compressed archive of the specified files and directories and upload them to a remote destination using rclone.

The backup process starts by ensuring that the required dependencies, such as zip and rclone, are installed on the system. The script then checks if rclone is configured by attempting to show the configuration settings. If rclone is not configured, the script prompts the user to run `rclone config` to configure it.

Next, the script defines the source directory, which is the directory that the user wants to backup. The script then checks if the source directory exists, and if not, it returns an error message and exits the script.

The script then creates a compressed archive of the source directory using the zip command and saves it with a filename that includes the current date and time. The script defines the backup destination, which is the remote location where the backup archive will be stored. In this project, the backup destination is set to a folder on the user's Google Drive. Finally, the script uses the rclone command to upload the backup archive to the defined backup destination and removes the backup archive from the local system to save space.

To automate the backup process, the user can schedule the backup script using cron, a time-based job scheduler in Unix-like operating systems. Cron allows users to schedule jobs to run automatically at specified times and frequencies.

To schedule the backup script using cron, the user needs to add a new job to the cron table. The job should include the command to execute the backup script using bash, along with the desired schedule for the backup.

For example, to schedule the backup script to run every day at 2:33 AM, the user can add the following job to the cron table:
```SHELL
33 2 * * * bash /home/kratospidey/krato/ab.sh
```

The above cron job will execute the backup script named 'ab.sh' every day at 2:33 AM. The backup process will then run automatically without any manual intervention required.

In summary, the Automatic Backup System provides a reliable and automated backup solution for Linux users. The project uses Bash scripting language to create a compressed archive of the specified files and directories and upload them to a remote destination using rclone. By scheduling the backup script using cron, the backup process can be executed automatically at a user-defined time and frequency, without any manual intervention required.
# New Commands Used
1. `which` - checks if a command is available on the system and returns the path to the command if it is available.
2.  `zip` - a command-line utility for creating and manipulating compressed archive files in the ZIP format.
3.  `rclone` - a command-line tool for working with various cloud storage providers, including Google Drive.
4.  `config` - a command used with rclone to configure the cloud storage provider to be used with rclone.
5.  `config show` - a command used with rclone to display the current rclone configuration settings.
6.  `date` - a command used to display the current date and time.
7.  `mkdir` - a command used to create a new directory.
8.  `rm` - a command used to remove (delete) files or directories.
9.  `zip -r` - a command used to create a compressed archive of a directory and its contents.
10.  `rclone copy` - a command used to copy files from the local system to a remote destination using rclone.
11.  `crontab -e` - a command used to edit the user's crontab file, which is used to schedule jobs to run automatically at specified times and frequencies.
12.  `chmod` - a command used to modify the permissions of a file or directory.
13.  `sudo service cron start` - a command used to start the cron service.
14.  `service cron status` - a command used to check the status of the cron service.
15.  `curl` - a command-line tool used to transfer data from or to a server using various protocols, including HTTP, HTTPS, FTP, and more.

First, the `curl https://rclone.org/install.sh | sudo bash` command is used to download and install rclone on the system.
Then in the Automatic Backup System, the `which` command is used to check if the `zip` and `rclone` commands are available on the system. The `config` and `config show` commands are used with `rclone` to check if it is configured and to configure it if it is not.

The `date` command is used to create a timestamp for the backup archive filename. The `mkdir` command is used to create the backup directory on the remote destination, if it does not already exist.

The `zip -r` command is used to create a compressed archive of the specified source directory. The `rclone copy` command is used to upload the backup archive to the remote destination using rclone. Finally, the `rm` command is used to remove the backup archive from the local system after it has been uploaded to the remote destination.

The `crontab -e` command is used to schedule the backup script to run automatically at specified times and frequencies. The `chmod` command may also be used to modify the permissions of the backup script to ensure that it can be executed by cron. The `sudo service cron start` command is used to start the cron service if it is not already running. The `service cron status` command is used to check the status of the cron service to ensure that it is running properly.

# Screenshots


# Code

```Bash
#!/bin/bash

# Check that zip and rclone are installed
if ! which zip >/dev/null; then
  echo "Error: zip command not found."
  exit 1
fi
if ! which rclone >/dev/null; then
  echo "Error: rclone command not found."
  exit 1
fi

# Check that rclone is configured
if ! rclone config show >/dev/null; then
  echo "Error: rclone not configured. Please run 'rclone config' to configure it."
  exit 1
fi

# Define the source directory
BASE_DIR="/home/kratospidey/krato"
SOURCE_DIR="$BASE_DIR/test"


# Check that the source directory exists
if [ ! -d "$SOURCE_DIR" ]; then
  echo "Error: Directory $SOURCE_DIR not found."
  exit 1
fi

# Define the backup file name and destination
BACKUP_NAME="backup_$(date +%Y-%m-%d_%H-%M-%S).zip"
BACKUP_DEST="GDRIVE:backup/$BACKUP_NAME"

# Compress the source directory into a zip file
zip -r "$BACKUP_NAME" "$SOURCE_DIR"

# Upload the backup file to Google Drive using rclone
rclone copy "$BACKUP_NAME" "$BACKUP_DEST"

# Remove the backup file from the local system
rm "$BACKUP_NAME"
```
# Conclusion

In conclusion, the Automatic Backup System project for Linux provides a simple and effective way to backup important files to a remote location using rclone. The bash script automates the entire process, from checking the availability of required tools to compressing the source directory into a zip file and uploading it to Google Drive via rclone. Additionally, the project also includes setting up a cron job to run the backup process at specified intervals automatically.

Overall, this project is an excellent solution for Linux users who need a reliable way to backup their important data automatically without having to do it manually every time. It can help users avoid data loss due to hardware failures, system crashes, or other unexpected events. By following the steps outlined in the tutorial, users can quickly and easily set up their own automated backup system and enjoy the peace of mind that comes with knowing their data is safe and secure.

---


