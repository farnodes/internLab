1. Archiving vs Compression

Archiving → Collecting multiple files/folders into a single file (without reducing size). Example: tar

Compression → Reducing file size using algorithms (gzip, bzip2, xz, zip).

Combined → First archive, then compress → .tar.gz, .tar.bz2, .tar.xz

🔹 2. Archiving with tar
Create archive
```bash
tar -cvf archive.tar file1 file2 dir1/
```
c → create
v → verbose (show progress)
f → file name
✅ Example:

```bash
tar -cvf backup.tar /home/user/Documents
```
Extract archive

```bash
tar -xvf archive.tar
```

✅ Extract to specific directory:

```bash
tar -xvf archive.tar -C /tmp/extracted/
```

List files in archive

```bash
tar -tvf archive.tar
```

🔹 4. Compression with bzip2
Tar + Bzip2

```bash
tar -cjvf backup.tar.bz2 /home/user/Documents
```

Extract:

```bash
tar -xjvf backup.tar.bz2
```
🔹 5. Compression with xz
Tar + XZ (better compression, slower)

```bash
tar -cJvf backup.tar.xz /home/user/Documents
```
Extract:

```bash
tar -xJvf backup.tar.xz
```
🔹 6. zip and unzip
Compress files into .zip

```bash
zip archive.zip file1 file2 dir1/
```

Extract .zip

```bash
unzip archive.zip
```

I think you mean gzip, bzip2, and maybe bz2 (bzip2). Let me break it clearly for you 👇


🔹 2. bzip2 (.bz2)

Slower than gzip, but better compression ratio.

Extension → .bz2

With tar:

tar -cjvf archive.tar.bz2 files/
tar -xjvf archive.tar.bz2


🔹 Comparison Table
Tool	Extension	Speed	Compression
gzip	.gz	Fast	Medium
bzip2	.bz2	Slower	Better
xz	.xz	Slowest	Best

👉 So, use gzip for speed, bzip2 for balance, and xz for max compression.

Do you want me to also cover xz (.xz) along with these, since it’s the more advanced successor of bzip2?

1. tar + gzip (.tar.gz or .tgz)

```bash
tar -czvf archive.tar.gz files/
```
c → create
z → gzip
v → verbose
f → filename

Extract:

```bash
tar -xzvf archive.tar.gz
```

2. tar + bzip2 (.tar.bz2)
```bash
tar -cjvf archive.tar.bz2 files/
```
Extract:

```bash
tar -xjvf archive.tar.bz2
```

3. tar + xz (.tar.xz)

```bash
tar -cJvf archive.tar.xz files/
```

J → xz
Extract:
```bash
tar -xJvf archive.tar.xz
```

🔹 Summary Table
Method	Tar Command (Create)	Extract Command	File Extension
gzip	tar -czvf archive.tar.gz files/	tar -xzvf archive.tar.gz	.tar.gz / .tgz
bzip2	tar -cjvf archive.tar.bz2 files/	tar -xjvf archive.tar.bz2	.tar.bz2
xz	tar -cJvf archive.tar.xz files/	tar -xJvf archive.tar.xz	.tar.xz

👉 So:

Use z for gzip

Use j for bzip2

Use J for xz