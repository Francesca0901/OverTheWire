# Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions

# Solution
```shell
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
```
- N-Z: Replace any uppercase letter from A-M with the corresponding uppercase letter from N-Z.
- A-M: Replace any uppercase letter from N-Z with the corresponding uppercase letter from A-M.
- n-z: Replace any lowercase letter from a-m with the corresponding lowercase letter from n-z.
- a-m: Replace any lowercase letter from n-z with the corresponding lowercase letter from a-m.