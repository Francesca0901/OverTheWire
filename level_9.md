# Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

# Solution
The basic command I used is:
```shell
bandit9@bandit:~$ strings data.txt | grep '=='
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
The `strings` command in Unix or Linux is used to find and print all the printable strings from a binary file or any other object file.

- passwd:`G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s`