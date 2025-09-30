1. What is Package Management?

A package manager is a tool used to install, update, remove, and manage software on Linux. It automatically handles dependencies.

Debian/Ubuntu → apt / dpkg

RHEL/CentOS/Fedora → yum / dnf / rpm

2. Basic Package Management
Ubuntu/Debian (APT)

1️⃣ Update package index

```bash
sudo apt update
```

Refreshes the list of available packages and their versions.

2️⃣ Install a package

```bash
sudo apt install nginx
```

Installs Nginx web server and required dependencies.

3️⃣ Remove a package

```bash
sudo apt remove nginx
```
Removes Nginx but keeps configuration files.

4️⃣ Purge a package

```bash
sudo apt purge nginx
```

Removes Nginx and configuration files.

5️⃣ Upgrade all packages

```bash
sudo apt upgrade
```

6️⃣ Search for a package

```bash
apt search apache2
```

RHEL/CentOS (YUM/DNF)


1️⃣ Update package index

```bash
sudo yum check-update
```

2️⃣ Install a package

```bash
sudo yum install httpd
```

3️⃣ Remove a package

```bash
sudo yum remove httpd
```

4️⃣ Upgrade packages

```bash
sudo yum update
```

5️⃣ Search for a package

```bash
yum search nginx
```
