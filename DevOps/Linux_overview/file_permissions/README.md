🔹 1. View File Permissions
```bash
ls -l
```
$ ls -l 
-rw-r--r-- 1 rahul rahul  4096 Sep 24  file.txt

Explanation:

-rw-r--r-- → permissions

1 → number of hard links

rahul → owner

rahul → group

4096 → file size in bytes

Sep 24 → last modified date

file.txt → file name

🔹 2. Change File Permissions – chmod
chmod [options] permissions file_name
Numeric Mode Example:

```bash
chmod 755 script.sh
```
7 = read + write + execute for owner

5 = read + execute for group

5 = read + execute for others


Symbolic Mode Example:

```bash
chmod u+x file.txt
```

Adds execute (+x) for user (owner).

u=user, g=group, o=others, a=all

Remove permission:

```bash
chmod o-r file.txt
```
Removes read for others.

🔹 3. Change File Ownership – chown

chown [owner]:[group] file_name

Examples:

```bash
chown root file.txt
```

Changes owner to root.

```bash
chown rahul:developers file.txt
```

Changes owner to rahul and group to developers.

Recursive:

```bash
chown -R rahul:rahul /var/www
```

Changes ownership for all files & subdirectories.

🔹 4. Change Group Ownership – chgrp

```bash
chgrp group_name file_name
```
Example:
chgrp developers file.txt


Changes only the group.
Recursive:
```bash
chgrp -R developers /var/www
```

🔹 5. Special Permissions
(a) Setuid – Execute as File Owner

```bash
chmod u+s file
```
When executed, runs with the owner’s privileges.

(b) Setgid – Execute as Group Owner

```bash
chmod g+s dir/
```
New files inside dir/ inherit the group.

(c) Sticky Bit – Protect Files in Shared Directory

```bash
chmod +t /shared
```

Users can only delete their own files in /shared.

Check:

ls -ld /shared
drwxrwxrwt ...

🔹 6. Default Permissions – umask

View default mask:

```bash
umask
```

Set new umask:

```bash
umask 022
```

New files: 644

New directories: 755

🔹 7. Access Control Lists (ACLs) (Advanced)

Install ACL support (if not installed):

```bash
sudo apt install acl
```

Add ACL:

```bash
setfacl -m u:rahul:rwx file.txt
```

Gives user rahul rwx permissions on file.txt.

View ACL:

```bash
getfacl file.txt
```

Remove ACL:

```bash
setfacl -x u:rahul file.txt
```

Remove all ACL:
```bash
setfacl -b file.txt
```
🔹 8. Check File Type + Inode Info

```bash
stat file.txt
```

Shows permissions, inode, size, timestamps.

🔹 9. Find Files by Permission

```bash
find / -perm 777
```

Lists all files with 777 permission.

🔹 10. Practical Ownership + Permission Scenario

Step 1: Create directory

```bash
mkdir /var/www/project
```
Step 2: Set ownership
```bash
chown -R www-data:www-data /var/www/project
```
Step 3: Give execute permission to owner

```bash
chmod 750 /var/www/project
```