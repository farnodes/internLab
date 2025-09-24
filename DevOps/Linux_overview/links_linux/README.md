🔹 1. Hard Links

A Hard Link is like another name for a file.

It points directly to the same inode as the original file.

Both files share the same data blocks.

If you delete the original file, the hard link still works because the data still exists on disk.

📝 Basic Syntax:
```bash
ln <source_file> <hard_link_name>
```
📝 Example:
# Create a file

```bash
echo "Hello Linux" > file1.txt
```
# Create a hard link

```bash
ln file1.txt file1_hardlink.txt
```
# Check inode numbers

```bash
ls -li
```
Output:

12345 -rw-r--r-- 2 rahul rahul 12 Sep 24 16:00 file1.txt
12345 -rw-r--r-- 2 rahul rahul 12 Sep 24 16:00 file1_hardlink.txt

🔹 Notice both files have same inode number.
🔹 Both point to same data.

🔹 2. Soft (Symbolic) Links

A Soft Link (Symbolic Link) is like a shortcut.

It points to the path of the file, not its inode.

If you delete the original file, the link becomes broken.

They can point to directories too (hard links cannot for directories in most systems).

📝 Basic Syntax:

```bash
ln -s <source_file_or_directory> <link_name>
```
📝 Example:
# Create a symbolic link

```bash
ln -s file1.txt file1_symlink.txt
```
# Check details

``bash
ls -li
```
Output:
67890 lrwxrwxrwx 1 rahul rahul 10 Sep 24 16:02 file1_symlink.txt -> file1.txt

🔹 Notice the arrow (->).
🔹 Different inode numbers.

🔹 3. Verify Links


Use these commands:

```bash
ls -li        # Inode numbers
stat filename # Detailed file status (including link count)
readlink -f filename # Resolve the actual path of a symlink
```

🔹 4. Advanced Examples
(a) Hard Link Advanced Usage
# Create multiple hard links to the same file

```bash
ln file1.txt file1_hardlink2.txt
ln file1.txt file1_hardlink3.txt
```
# Check link count (nlink)

```bash
stat file1.txt
```
(b) Symbolic Link to Directory
# Create a directory
```bash
mkdir mydir
```
# Create a symlink to directory

```bash
ln -s mydir mydir_link
```
# Now use 'cd mydir_link' to access the directory

```bash
cd mydir_link
```
(c) Broken Symlink Detection
# Delete original file

```bash
rm file1.txt
```
# Now check symlink

```bash
ls -l file1_symlink.txt
```
Output:

lrwxrwxrwx 1 rahul rahul 10 Sep 24 16:02 file1_symlink.txt -> file1.txt

Color/ls shows red or “No such file” when accessed.

(d) Update Symlink Target
# Change where a symlink points

```bash
ln -snf newfile.txt file1_symlink.txt
```

🔹 -n prevents dereferencing
🔹 -f forces overwrite

🔹 This lists all files with the same inode.

(f) Remove a Link

# For hard link - just delete file
```bash
rm file1_hardlink.txt
```
# For soft link - only the link is deleted, not the original

```bash
rm file1_symlink.txt
```
