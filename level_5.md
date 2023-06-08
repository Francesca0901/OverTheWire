# Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
- human-readable
- 1033 bytes in size
- not executable

A brief view of what's in our system:
```shell
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ cd maybehere00
bandit5@bandit:~/inhere/maybehere00$ ls -al
total 72
drwxr-x---  2 root bandit5 4096 Apr 23 18:04 .
drwxr-x--- 22 root bandit5 4096 Apr 23 18:04 ..
-rwxr-x---  1 root bandit5 1039 Apr 23 18:04 -file1
-rwxr-x---  1 root bandit5  551 Apr 23 18:04 .file1
-rw-r-----  1 root bandit5 9388 Apr 23 18:04 -file2
-rw-r-----  1 root bandit5 7836 Apr 23 18:04 .file2
-rwxr-x---  1 root bandit5 7378 Apr 23 18:04 -file3
-rwxr-x---  1 root bandit5 4802 Apr 23 18:04 .file3
-rwxr-x---  1 root bandit5 6118 Apr 23 18:04 spaces file1
-rw-r-----  1 root bandit5 6850 Apr 23 18:04 spaces file2
-rwxr-x---  1 root bandit5 1915 Apr 23 18:04 spaces file3
```

# Solution
```shell
bandit5@bandit:~/inhere$ find . -size 1033c ! -executable
./maybehere07/.file2
```
The `c` stands for bytes, which is the standard unit of measurement for file sizes in most file systems and operating systems.

- passwd: `P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU`