# Experiment 9: Shell Programming
**Name:** Keshav Chadha
**Roll No.:** 590029233

# Requirements:
* Operating System: Ubuntu running on Oracle VirtualBox
* Shell: Bash (Bourne-Again Shell)
***
***
# Theory
## 1. System Performance Monitoring
* `top` → live CPU & memory usage per process.
![](./images/901.png)
* `htop` → improved version of `top` (if installed).
![](./images/902.png)
* `free -h` → memory usage in human-readable form.
![](./images/903.png)
* `df -h` → disk space usage.
![](./images/904.png)
* `iostat` → input/output statistics (may need `sysstat` package).
![](./images/905.png)
* `uptime` → system load averages (1, 5, 15 minutes).
![](./images/906.png)

## 2. System Security and User Management
* `whoami` → current user.
![](./images/907.png)
* `id` → user & group info.
![](./images/908.png)
* `groups` → display user’s groups.
![](./images/909.png)

# Lab
## i. Rename All Files in a Directory
```bash
#!/bin/bash
echo "Enter directory path:"
read dir
echo "Enter prefix or suffix to add:"
read add

cd "$dir" || { echo "Directory not found!"; exit 1; }

for file in *; do
    if [ -f "$file" ]; then
        mv "$file" "${add}_$file"
    fi
done
echo "Files renamed successfully."
```

Output:
![](./images/910.png)

## ii. Search Files by Extension or Size
```bash
#!/bin/bash
echo "Enter directory to search:"
read dir
echo "Enter file extension (e.g. .txt):"
read ext
echo "Enter minimum size in KB:"
read size

find "$dir" -type f -name "*$ext" -size +"${size}k"
```

Output:
![](./images/911.png)

## iii. Fibonacci Series
```bash
#!/bin/bash
echo "Enter the number of terms:"
read n

a=0
b=1
echo "Fibonacci Series:"
for ((i=0; i<n; i++))
do
    echo -n "$a "
    fn=$((a + b))
    a=$b
    b=$fn
done
echo
```

Output:
![](./images/912.png)

***

# OBERVATIONS
*

***

# CONCLUSION
The experiment helped in understanding advanced file and directory operations in Linux, enhancing efficiency in file management through searching, archiving, compression, and linking techniques.


***
