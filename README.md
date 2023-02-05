# sshd_config hardened file
🎯 This repository hosts my hardened version of OpenSSH server on [OpenBSD](https://www.openbsd.org).

📝 Here the [man](https://man.openbsd.org/sshd_config) for sshd_config.

🛡️ Too many admins overlook SSH configuration when setting up new systems. Unfortunately, the defaults for many operating systems are optimized for compatibility, **not security**❗

## Prerequisites
 * You need to have an account with doas set correctly.
 * You need to create a key for your user:
   * `ssh-keygen -f ~/user-key-ed25519 -t ed25519` -> Enter a Passphrase please 😉
   * `ssh-copy-id -i ~/.ssh/user-key-ed25519 user@host_destination:/.....`
Once the public key has been configured on the server, the server will allow any connecting user that has the private key to log in. During the login process, the client proves possession of the private key by digitally signing the key exchange.

## Usage
* Backup your current file like this:
  * cp `/etc/ssh/sshd_config` `/etc/ssh/sshd_config.ori`
* Download the file `sshd_config` from the repository in your local terminal session
* Review the content of the `sshd_config` file to make sure those settings are suitable with your configuration:
  * Search AllowUsers and replace your_username_here with your username
  * Search Banner and replace /your_path_here/your_file_here with the right path file for your banner
* Overwrite your file:
  * mv `ssh_config` `/etc/ssh_sshd/config`
* Reload SSHDaemon
  * `rcctl restart sshd`

## Blueteam - Check new settings
You can test your OpenSSH server configuration here:
  * [SSH Audith](https://www.sshaudit.com/) 
  * [SSH Check](https://sshcheck.com/)

🐡 Have Fun!
