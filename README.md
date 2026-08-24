# AWS EC2 Linux SSH Administration

## Project Overview

This project demonstrates how to launch and securely access an Amazon EC2 instance running Amazon Linux 2023. I configured SSH access using an EC2 key pair, secured the private key locally, connected to the instance through the macOS Terminal, and practiced basic Linux administration commands.

The project was created to strengthen my hands-on AWS, Linux, networking, security, and cloud administration skills.

## Technologies Used

* Amazon Web Services (AWS)
* Amazon EC2
* Amazon Linux 2023
* AWS Security Groups
* SSH
* Linux Command Line
* macOS Terminal
* Public-Key Authentication

## Architecture

```text
MacBook
   |
   | SSH - Port 22
   |
Internet
   |
AWS Security Group
   |
Amazon EC2 Instance
   |
Amazon Linux 2023
```

## Implementation Steps

### 1. Launched an EC2 Instance

Created an Amazon EC2 instance using the Amazon Linux 2023 AMI.

Configured the instance with the appropriate instance type, networking settings, and SSH access.

### 2. Configured an EC2 Key Pair

Created and used an EC2 key pair named:

```text
EC2Git.pem
```

The private key was downloaded and stored securely on my local Mac.

> The private key file is intentionally excluded from this repository and is never uploaded to GitHub.

### 3. Configured the Security Group

Configured the EC2 security group to allow SSH traffic through:

```text
Protocol: TCP
Port: 22
Service: SSH
```

SSH access was configured to allow secure remote administration of the EC2 instance.

### 4. Secured the Private Key

Restricted permissions on the private key using:

```bash
chmod 400 /Users/yanykamac/Documents/AWS\ Course/EC2Git.pem
```

This ensures that the private key can only be accessed by the local user.

### 5. Connected to the EC2 Instance Using SSH

Connected to the Amazon Linux instance from macOS Terminal using SSH:

```bash
ssh -i /Users/yanykamac/Documents/AWS\ Course/EC2Git.pem ec2-user@44.200.7.10
```

After authentication, the terminal displayed the Amazon Linux 2023 environment and changed from the local Mac terminal prompt to the EC2 Linux user prompt.

Example:

```text
[ec2-user@ip-172-31-xx-xx ~]$
```

### 6. Verified the Linux Environment

After connecting to the EC2 instance, I used several Linux commands to verify the operating system, current user, system information, and working directory.

```bash
pwd
whoami
hostname
uname -a
cat /etc/os-release
ls -la
```

These commands helped confirm that I was successfully operating inside the Amazon Linux EC2 instance rather than my local computer.

### 7. Practiced Linux File and Directory Management

Created a project directory:

```bash
mkdir cloud-project
```

Navigated into the directory:

```bash
cd cloud-project
```

Created a test file:

```bash
touch test.txt
```

Verified the files in the directory:

```bash
ls -la
```

Checked the current working directory:

```bash
pwd
```

### 8. Created and Read a Text File

Created a text file from the Linux command line:

```bash
echo "AWS EC2 Linux SSH Project" > project.txt
```

Displayed the contents of the file using:

```bash
cat project.txt
```

This demonstrated basic Linux file creation, output redirection, and file-reading commands.

### 9. Exited the Remote EC2 Session

After completing the Linux exercises, I ended the SSH session using:

```bash
exit
```

This returned the terminal session to my local Mac.

## Security Considerations

Several security practices were followed during this project:

* The private `.pem` key is not stored in GitHub.
* Private key permissions were restricted using `chmod 400`.
* SSH was used for encrypted remote access.
* Sensitive AWS credentials were excluded from project documentation.
* AWS access keys, secret keys, passwords, and session tokens are never included in screenshots or repository files.
* A `.gitignore` file is used to prevent private key files from being committed accidentally.

## .gitignore

The following entries were added to `.gitignore`:

```text
*.pem
*.key
.env
```

## Screenshots

### Screenshot 1 — EC2 Instance Running

Shows the EC2 instance successfully launched and in the **Running** state.

Suggested filename:

```text
01-ec2-instance-running.png
```

### Screenshot 2 — Security Group SSH Configuration

Shows the EC2 security group inbound rule allowing SSH communication over TCP port 22.

Suggested filename:

```text
02-security-group-ssh.png
```

### Screenshot 3 — Successful SSH Connection

Shows the successful SSH connection from macOS Terminal to the Amazon Linux 2023 EC2 instance.

Suggested filename:

```text
03-successful-ssh-login.png
```

### Screenshot 4 — Linux System Information

Shows commands such as:

```bash
whoami
cat /etc/os-release
```

This confirms the active user and Amazon Linux 2023 operating system.

Suggested filename:

```text
04-linux-system-info.png
```

### Screenshot 5 — Linux File Management

Shows the creation and navigation of the `cloud-project` directory and files within it.

Suggested filename:

```text
05-linux-file-management.png
```

### Screenshot 6 — Text File Creation

Shows the creation and contents of:

```text
project.txt
```

using:

```bash
echo "AWS EC2 Linux SSH Project" > project.txt
cat project.txt
```

Suggested filename:

```text
06-linux-text-file.png
```

## Repository Structure

```text
aws-ec2-linux-ssh/
│
├── README.md
├── .gitignore
│
└── screenshots/
    ├── 01-ec2-instance-running.png
    ├── 02-security-group-ssh.png
    ├── 03-successful-ssh-login.png
    ├── 04-linux-system-info.png
    ├── 05-linux-file-management.png
    └── 06-linux-text-file.png
```

## Skills Demonstrated

* Amazon EC2 deployment
* Amazon Linux 2023 administration
* Linux command-line navigation
* SSH remote server access
* EC2 key pair authentication
* Linux file permissions
* Linux file and directory management
* AWS Security Groups
* TCP/IP networking fundamentals
* SSH port 22 configuration
* Public-key authentication
* Cloud server administration
* macOS Terminal
* AWS security fundamentals

## What I Learned

This project gave me hands-on experience connecting a local computer to cloud infrastructure and administering a Linux server hosted in AWS.

I learned how EC2 key pairs are used for SSH authentication, why private key permissions must be secured, how AWS Security Groups control network access, and how to use basic Linux commands after connecting to a remote cloud server.

I also gained experience creating directories, managing files, reviewing operating system information, and working directly inside an Amazon Linux environment.


