GREP
====

Grep stands for **Global Regular Expression Print**. It was created
in the 70's and it is still a butt-kicking command line tool.



## Basic ##

Print lines containing <code>yoda</code>:

    grep 'Yoda' users.txt


NOTE: Grep is **Case Sensitive**. Uppercase and lowercase letters do make difference.


Print lines containing <code>Yoda</code>, <code>yoDA</code>, <code>YODA</code>, or
any combination of uppercase and lowercase letters.

    grep --ignore-case 'yoda' users.txt

or

    grep -i 'yoda' users.txt


To print the line number where the matches happen, do:

    grep --line-number 'Yoda' users.txt

or

    grep -n 'Yoda' users.txt


It is possible to combine command-line options, as in any unix-like command-line tool:

    grep --line-number --ignore-case 'yoda' users.txt

or

    grep -n -i 'yoda' users.txt

or

    grep --ignore-case -n 'yoda' users.txt

or

    grep -in 'yoda' users.txt
