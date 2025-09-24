1️⃣ pwd – Print Working Directory

Purpose: Shows your current directory path in the filesystem.
```bash
$ pwd
/home/rahul
```
Explanation:
You are currently in the /home/rahul directory.

2️⃣ ls – List Files and Directories

Purpose: Lists files and folders in the current directory.
```bash
$ ls
Documents  Downloads  Music  Projects
```
Options:

ls -l → Detailed list with permissions, owner, size, and date.

ls -a → Show hidden files (files starting with .).
```bash
$ ls -la
drwxr-xr-x  5 rahul rahul 4096 Sep 24 15:00 .
drwxr-xr-x 20 rahul rahul 4096 Sep 24 14:00 ..
-rw-r--r--  1 rahul rahul   50 Sep 24 12:00 file.txt
```

3️⃣ cd – Change Directory

Purpose: Move between directories.
```bash
$ cd Documents
$ pwd
/home/rahul/Documents
```
Tips:

cd .. → Go to the parent directory

cd ~ → Go to your home directory

cd / → Go to root directory


4️⃣ mkdir / rmdir – Make / Remove Directories

mkdir – Create a directory
```bash
$ mkdir MyFolder
$ ls
Documents  Downloads  MyFolder
```

rmdir – Remove an empty directory
```bash
$ rmdir MyFolder
$ ls
Documents  Downloads
```
Note: If the directory has files, rmdir will fail. You need rm -r MyFolder to remove it recursively.

5️⃣ touch – Create Empty Files

Purpose: Quickly create an empty file or update file timestamp.
```bash
$ touch file1.txt
$ ls
file1.txt  Documents  Downloads
```

6️⃣ cp / mv / rm – Copy, Move, Remove Files

cp – Copy files
```bash
$ cp file1.txt file2.txt
```
$ ls

```bash
file1.txt  file2.txt
```

mv – Move or rename files
```bash
$ mv file2.txt file3.txt
```

$ ls
```bash
file1.txt  file3.txt
```

rm – Remove files
```bash
$ rm file3.txt
```
$ ls
```bash
file1.txt
```

Note: Be careful with rm. Use rm -i file.txt for confirmation.

7️⃣ cat, less, more, head, tail – View File Contents

cat – Display full file content
```bash
$ cat file1.txt
Hello World
```

less – View file one page at a time (scrollable)
```bash
$ less file1.txt
# Use ↑↓ to scroll, q to quit
```

more – Similar to less, but older
```bash
$ more file1.txt
```
# Navigation inside more:

Space → Next page

Enter → Next line

b → Back one page

q → Quit

head – View first 10 lines (default)

```bash
$ head file1.txt
Hello World
```

tail – View last 10 lines (default)

```bash
$ tail file1.txt
Hello World
```

