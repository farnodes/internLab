1. Redirect Output to a File
> : Overwrites the file with command output.

```bash
echo "Hello World" > file.txt
```
# file.txt now contains: Hello World
>> : Appends output to the file.

```bash
echo "Another line" >> file.txt
```
# file.txt now contains:
# Hello World
# Another line

2. Redirect Input from a File
< : Takes input from a file instead of the keyboard.
sort < file.txt
# Sorts lines from file.txt and prints to stdout

3. Pipe Output to Another Command

| : Sends the output of one command as input to another.

```bash
cat file.txt | grep "Hello"
```
# Finds lines containing "Hello"

4. Redirect Output to Both File and Console

tee : Writes output to a file and displays it on the terminal.

```bash
echo "Logging this line" | tee log.txt
```
# Displays: Logging this line
# Saves it to log.txt


Append mode with tee -a

echo "Another log" | tee -a log.txt

5. Advanced Redirection

Redirect stderr (errors)

```bash
ls /no/such/dir 2> error.log   # 2> redirects stderr
```
```bash
ls /no/such/dir > out.log 2>&1 # Redirect both stdout & stderr
```

Combine multiple pipes

cat file.txt | grep "pattern" | sort | uniq

