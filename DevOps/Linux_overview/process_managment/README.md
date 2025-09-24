1. Viewing Processes

a. ps – Snapshot of current processes

```bash
ps               # Show processes of current shell
```

```bash
ps aux           # Show all processes with detailed info
```

```bash
ps -ef           # Alternative format, widely used
```
```bash
ps -u username   # Show processes of a specific user
```

Example:

ps aux | grep nginx


Lists all processes containing “nginx”.

b. top – Interactive real-time process monitoring

```bash
top
```

Key commands inside top:

P – Sort by CPU usage

M – Sort by memory usage

k – Kill a process by PID

q – Quit

c. htop – Enhanced interactive top (needs installation)

```bash
sudo apt install htop  # Ubuntu/Debian
```
```bash
htop
```

Features:

Color-coded CPU, memory, swap

Scrollable process list

Kill, renice processes interactively

2. Terminating Processes

a. kill – Kill a process by PID

```bash
kill 1234           # Send default SIGTERM
kill -9 1234        # Force kill (SIGKILL)
```


b. killall – Kill processes by name

killall firefox


Useful when multiple processes have the same name.

3. Background & Foreground Jobs

a. jobs – List background jobs in current shell

```bash
sleep 100 &         # Run process in background
```
```bash
jobs                # List jobs
```


b. fg – Bring a job to foreground

```bash
fg %1               # Bring job 1 to foreground
```

c. bg – Resume a stopped job in background

```bash
bg %1               # Resume job 1 in background
```

4. Advanced Process Management

a. nice & renice – Adjust process priority

```bash
nice -n 10 command      # Start with lower priority
```
```bash
renice -n 5 -p 1234     # Change priority of running process
```


b. pmap – Memory map of a process

```bash
pmap 1234
```

c. lsof – List open files (useful to check which process uses a file/port)

```bash
lsof -i :80           # Check process using port 80
```

d. pstree – View process hierarchy/tree

```bash
pstree -p
```