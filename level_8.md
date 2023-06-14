# Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

# Helpful Reading Material
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)

# Solution
1. `sort data.txt | uniq -d`: This sorts the lines in data.txt and then uses uniq -d to only display duplicate lines. This helps us identify lines that occur more than once.  
   1. by default `uniq` compares lines in the input and removes any consecutive duplicates
   2. The `-d` option modifies the behavior of uniq to only display duplicate lines. 
    ```shell
    bandit8@bandit:~$ sort data.txt | uniq -d
    08Jd2vmb6FjR4zXPteGHhpJm8A0OOA5B
    0dEKX1sDwYtc4vyjrKpGu30ecWBsDDa9
    0YDTDPCLc585IaFu911ukE9QfD6Ykrlz
    0zP9wfUcMKjZM2hiQUYR1nTfmaRdYSQE
    11FFcDRW5ZXXmX7geZORYRwiJfj8B3Gh
    1jZv2X1O2JypCBIgDNRwWQzS1CyhvByt
    1MUdfR7bGGCpNfGEOXaIEdrA8hT2L8Tk
    2fepTygKSkWHQJS2GrmGwjyl36eXSWJe
    3cTCUFe6MTl1FDAL0Z49cRByfq1MRlxJ
    3PB0nBOh1WKb1K6MImHdvwQjItFcxfdF
    3QXFsSepZUIOznxndwnQNnxvbpcXG05c
    47eFxPAuZ4tlWbT4P5ADs1tC0twlr51V
    4aOtDpqjXGIMOcyqirndla7J8S3jZZAy
    4Fi1Ig3hG4mDdl64v3gRPre3qNx26k0U
    4u67BT7FonRZeibEb9iOl6pHcMtzq03H
    6R258gRryXf9CBoG6erTEgGjb8ykWYrV
    ......
    ```
2. `<(...)`: This is process substitution in Bash. It allows us to treat the output of `sort data.txt | uniq -d` command as a file-like input.
3. `grep -vxFf`: The -v option inverts the match, -x matches whole lines, and -F treats the pattern as a fixed string rather than a regular expression. -f specifies a file to read patterns from.

So we use:
```shell
bandit8@bandit:~$ grep -vxFf <(sort data.txt | uniq -d) data.txt
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
The purpose of including `data.txt` again at the end is to provide the input file that grep will search through. The output of the command `<(sort data.txt | uniq -d)` is a list of duplicate lines generated from `data.txt`, and `grep -vxFf` compares those lines against the content of `data.txt`.