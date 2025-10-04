# Crontab (CRON Table) is a file that contains a list of commands to be executed automatically at specified times and dates.
Cron is the daemon/service that runs scheduled jobs in Linux.
1. Check if Cron is already installed. Open a terminal and run:

```bash
cron --version
```
If it shows version info → cron is installed.

If it shows command not found, we need to install it.

2. Install Cron On Ubuntu 22.04, use apt:
```bash
sudo apt update
sudo apt install cron
```
apt update → updates package lists

apt install cron → installs cron daemon

3. Start and Enable Cron Service
After installation, ensure cron service is running:

```bash
sudo systemctl start cron      # start cron service
sudo systemctl enable cron     # enable cron to start at boot
```
Check status:

systemctl status cron Active (running) → cron is working. If inactive, you can restart:

```bash
sudo systemctl restart cron
```

4. Basic Cron Usage

List your cron jobs:

```bash
crontab -l
```

Edit your cron jobs:

```bash
crontab -e
```

Remove all cron jobs:

```bash
crontab -r
```

5. Crontab Syntax (Structure)

```bash
* * * * * command_to_run
- - - - -
| | | | |
| | | | ----- Day of week (0-7) (Sunday=0 or 7)
| | | ------- Month (1-12)
| | --------- Day of month (1-31)
| ----------- Hour (0-23)
------------- Minute (0-59)
```

6. Testing Cron Jobs Simple test command:

```bash
* * * * * echo "Cron is working" >> /home/user/cron_test.log
```




