# Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

# Solution
I first check the size of the files:
```shell
bandit4@bandit:~/inhere$ du ./-file0*
4	./-file00
4	./-file01
4	./-file02
4	./-file03
4	./-file04
4	./-file05
4	./-file06
4	./-file07
4	./-file08
4	./-file09
```
but with no found.

Then I come up with a loop idea:
```shell
bandit4@bandit:~/inhere$ for file in ./-file*; do file "$file"; done
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators
```

Well maybe I can simply do:
```shell
bandit4@bandit:~/inhere$ file ./-file*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators
```

And finally we got it:
```shell
bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```

- passwd: `lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR`