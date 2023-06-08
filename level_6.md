# Level Goal
The password for the next level is stored **somewhere on the server** and has all of the following properties:
- owned by user bandit7
- owned by group bandit6
- 33 bytes in size

# Solution
```shell
bandit6@bandit:~$ find / -type f -user bandit7 -group bandit6 2>/dev/null
./var/lib/dpkg/info/bandit7.password
```
- `/` means we are searhing within the whole server
- `-type f` means we are searching for file type
- `-user` and `-group` are quite straightforward
- `2>/dev/null` is used to redirect any error messages to the null device, so you only see the output that matches the search criteria. 

So now we can see:
```shell
bandit6@bandit:/$ cat ./var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

- passwd: `z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S`