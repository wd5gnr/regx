# Regx & Litgrep

Simple script to convert things like:

    begin digit repeat 5 space one_or_more digit repeats 2 5
   
Into:

    ^[[:digit:]]{5}[[:space:]]+[[:digit:]]{2,5}
   
Use it as a command expansion:

    egrep $( regx any_of A-Z X zero_or_more )

In addition, you can use litgrep:

    litgrep any_of A-Z digit -- file1.txt file2.txt

# Mappings

* any_char - .
* zero_or_more - *
* one_or_more - +
* start - ^
* end - $
* digit - [[:digit:]]
* not_digit - [^[:digit:]]
* alpha - [[:alpha:]]
* not_alpha - [^[:alpha:]]
* blank - [[:blank:]]
* not_blank - [^[:blank:]]
* space - [[:space:]]
* not_space - [^[:space:]]
* or - |
* optional - ?
* open_group - (
* close_group - )
* any_of X - [X]
* none_of X - [^X]
* group X - (X)
* hex ff - \xff
* repeat 5 - {5}
* repeats 1 5 - {1,5}
* at_least 3 - {3,}
* literal ABC - ABC
* range A Z A-Z
* cr, lf, tab, bell, esc, ff, vt - special characters
