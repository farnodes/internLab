1. Identify Current User & Groups
whoami         # Shows the current logged-in username
id             # Shows UID, GID, and groups of the current user
groups         # Lists all groups the user belongs to

```bash
$ whoami
```
rahul

```bash
$ id
```
uid=1001(rahul) gid=1001(rahul) groups=1001(rahul),27(sudo)

2. Adding Users
```bash
udo useradd username
```
```bash
sudo passwd username     # Set password for the user
```
With Options:
sudo useradd -m -d /home/rahul -s /bin/bash rahul

# -m : create home directory
# -d : specify home directory
# -s : specify shell


Example:
```bash
sudo useradd -m -s /bin/bash rahul
```
```bash
sudo passwd rahul
```
3. Modifying Users

```bash
sudo usermod -l newname oldname          # Change username
```
```bash
sudo usermod -d /new/home -m username   # Change home directory and move files
```
```bash
sudo usermod -s /bin/zsh username       # Change default shell
```
```bash
sudo usermod -aG groupname username     # Add user to a group (append)
```
```bash
sudo usermod -G group1,group2 username  # Replace groups
```

Example:

```bash
sudo usermod -aG sudo rahul   # Add rahul to sudo group
```
```bash
sudo usermod -s /bin/zsh rahul # Change shell to zsh
```

4. Deleting Users

```bash
sudo userdel username          # Delete user
```
```bash
sudo userdel -r username       # Delete user + home directory
```

Example:

```bash
sudo userdel -r rahul
```

5. Group Management
Adding a Group:
```bash
sudo groupadd groupname
```
Deleting a Group:

```bash
sudo groupdel groupname
```
Modifying User Groups:

```bash
sudo usermod -aG groupname username  # Add user to group
```
Example:
```bash
sudo groupadd devteam
```
```bash
sudo usermod -aG devteam rahul
```
6. Changing Passwords
```bash
passwd                # Change own password
```
```bash
sudo passwd username  # Change another user's password
```

Example:
```bash
sudo passwd rahul
```
7. Viewing Users and Groups

```bash
cat /etc/passwd        # List all users
```
```bash
cat /etc/group         # List all groups
```
getent passwd username # Detailed info for a user

8. Advanced Tips
Lock/Unlock Users:

```bash
sudo usermod -L username  # Lock user
```
```bash
sudo usermod -U username  # Unlock user
```

Expire Accounts:

```bash
sudo chage -E 2025-12-31 username   # Set account expiration
```
```bash
sudo chage -l username               # Show password/account expiry info
```

Force Password Change on Next Login:

```bash
sudo passwd -e username
```

Check User Last Login:

```bash
last username
```

Switch Users:

```bash
su - username     # Switch to another user
```

```bash
sudo su -         # Switch to root
```