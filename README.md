# Seheyah's hardened OpenSSH server configuration
🎯 This repository hosts my hardened version of OpenSSH server on OpenBSD.

🛡️ Too many admins overlook SSH configuration when setting up new systems. Unfortunately, the defaults for many operating systems are optimized for compatibility, **not security**❗

## Usage
* Backup your current file like this:
  * cp `/etc/ssh/sshd_config` `/etc/ssh/sshd_config.ori`
* Download the file `sshd_config` from the repository in your local terminal session
* Review the content of the `sshd_config` file to make sure those settings are suitable with your configuration
  * Search AllowUsers and replace your_username_here with your username
  * Search Banner and replace /your_path_here/your_file_here with the right path file for your banner
* Overwrite your file:
  * mv `ssh_config` `/etc/ssh_sshd/config`
* Reload SSHDaemon
  * `rcctl restart sshd`

## Check new settings
You can test your OpenSSH server here:
  * [SSH Audith](https://www.sshaudit.com/) 
  * [SSH Check](https://sshcheck.com/)

Have Fun 🐡
