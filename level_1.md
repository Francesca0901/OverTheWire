# Level Goal
The password for the next level is stored in a file called `-` located in the home directory

# Helpful Reading Material
- [Google Search for “dashed filename”](https://www.google.com/search?q=dashed+filename)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](https://tldp.org/LDP/abs/html/special-chars.html)

# Solution
```shell
bandit1@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit2 bandit1 33 Apr 23 18:04 -
```
That's why we made sure `-` is a file in essential.

`cat -` is not going to work
We should use `./-` instead or specify option `<` before the dash (-) file.
```shell
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$ cat < -
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
```

- passwd: `rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi`