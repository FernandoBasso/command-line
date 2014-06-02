GREP
====

Grep stands for **Global Regular Expression Print**. It was created
in the 70's and it is still a butt-kicking command line tool.



## Basic ##

Print lines containing `yoda`:

    grep 'Yoda' users.txt


NOTE: Grep is **Case Sensitive**. Uppercase and lowercase letters do make difference.


Print lines containing `Yoda`, `yoDA`, `YODA`, or
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


Print lines that DO NOT match the pattern.

    grep --invert-match 'Yoda' users.txt

or

    grep -v 'Yoda' users.txt


Count the number of lines where a match occurred. In this case, the number of lines
where a user name contains the letter "a":

    grep --count --ignore-case 'a' users.txt

or

    grep -ci 'a' users.txt


All of the above commands match partial words and partial lines.
That is, `will` will also match `willful` and `unwillingly` and `A willful person`.
Using the `-x` modifier, you match only full lines, that is, that pattern must match
the entire line.

If you file contains the lines

    A willful person.
    will
    unwillingly

then, to match the middle line ONLY, you must do something like:

    grep --line-regexp 'unwillingly' users.txt

or

    grep -x 'will' users.txt


