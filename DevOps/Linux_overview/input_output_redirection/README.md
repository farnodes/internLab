# Input/Output Redirection
🔹 1. Input Redirection (<)
This takes input from a file instead of the keyboard.
```bash
cat < file.txt
```
➝ cat will display the content of file.txt (input from file, not keyboard).

```bash
wc -l < file.txt
```
🔹 2. Output Redirection Overwrite (>)
➝ Sends output to a file, overwriting its previous content.
```bash
ls > files.txt
```
➝ Saves directory listing into files.txt (overwrites file).
```bash
echo "Hello Rahul" > hello.txt
```
➝ Creates or overwrites hello.txt with “Hello Rahul”.

```bash
date > now.txt
```
➝ Saves the current date/time into now.txt.

🔹 3. Output Redirection Append (>>)

➝ Sends output to a file but appends it instead of overwriting.

```bash
echo "Line 1" >> myfile.txt
```
➝ Adds “Line 1” to the end of myfile.txt.

```bash
ls >> files.txt
```
➝ Appends directory listing to files.txt.

```bash
date >> files.txt
```
# Try to list a file that doesn't exist

```bash
ls file1.txt file2.txt 2> error.txt
```
ls: cannot access 'file2.txt': No such file or directory

# Try again and append error

```bash
ls file3.txt 2>> error.txt
```

Now error.txt will have old + new errors.

Example 3: Redirect both output & error

```bash
ls existing.txt nonexistent.txt > output.txt 2> error.txt
```
```bash
ls existing.txt nonexistent.txt &> all.txt
```
Both output and errors go to all.txt

✅ Summary:

2> → Redirect errors (overwrite)

2>> → Redirect errors (append)

&> → Redirect both output and errors