# AWS EC2 Linux SSH Administration

## Project Overview

This project demonstrates how to launch and securely access an Amazon EC2 instance running Amazon Linux 2023. I configured SSH access using an EC2 key pair, secured the private key locally, connected to the instance through the macOS Terminal, and practiced basic Linux administration commands.

The project was created to strengthen my hands-on AWS, Linux, networking, and cloud administration skills.

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

Configured the instance with an appropriate instance type and network settings.

### 2. Created an EC2 Key Pair

Created an AWS EC2 key pair for secure SSH authentication.

The private `.pem` key was downloaded and stored locally.

> The private key is intentionally excluded from this repository.

### 3. Configured the Security Group

Configured a security group to allow SSH traffic on TCP port 22 from my IP address only, reducing unnecessary public exposure. 

### 4. Secured the Private Key

Changed the permissions of the private key so that it could only be accessed by the local user.

```bash
chmod 400 ~/path/to/EC2Tutorial.pem
```

### 5. Connected to the EC2 Instance

Used SSH from the macOS Terminal to remotely connect to the Amazon Linux EC2 instance.

```bash
ssh -i ~/path/to/EC2Tutorial.pem ec2-user@<PUBLIC-IP>
```

A successful connection displayed the Amazon Linux 2023 environment and changed the terminal prompt from the local Mac user to the EC2 user.

### 6. Practiced Linux Commands

After connecting to the EC2 instance, I practiced basic Linux commands used for cloud server administration.

```bash
pwd
whoami
ls -la
uname -a
cat /etc/os-release
```

I also practiced creating and navigating directories and files.

```bash
mkdir cloud-project
cd cloud-project
touch test.txt
ls -la
```

## Security Considerations

Several security practices were followed during this project:

* Private `.pem` keys are never uploaded to GitHub.
* Private key permissions were restricted using `chmod 400`.
* SSH was used for encrypted remote access.
* Sensitive AWS credentials were excluded from screenshots and documentation.
* Public IP addresses can be replaced with placeholders in documentation.

The following entries were added to `.gitignore`:

```text
*.pem
*.key
```

## Skills Demonstrated

* Amazon EC2 deployment
* Amazon Linux administration
* Linux command-line navigation
* SSH remote access
* EC2 key pair authentication
* Linux file permissions
* AWS Security Groups
* TCP/IP and port 22 concepts
* Public-key authentication
* Cloud server administration
* macOS Terminal
* AWS security fundamentals

## Screenshots

Suggested screenshots for this repository:

1. EC2 instance successfully running
2. Security group configuration
3. Successful Amazon Linux SSH connection
4. Linux commands executed inside the EC2 instance

Sensitive information such as private keys, AWS credentials, account numbers, and secret keys should never appear in screenshots.

## What I Learned

This project helped me understand how cloud engineers and solutions architects remotely administer Linux servers hosted in AWS.

I gained hands-on experience connecting a local computer to cloud infrastructure using SSH, securing authentication credentials, configuring network access, and working directly inside an Amazon Linux environment.

