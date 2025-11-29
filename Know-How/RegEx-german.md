![Image](/img/BannerBoat.jpg)

(image: pixabay.com)

Regular Expressions (RegEx) Cheat Sheet
=====================================================

... ![Bild](/img/MF.png) *By Markus Fleschutz* 🕑 *May 05, 2020*

## Anchors

```
^           start of string or start of line
$           end of string or end of line
\b          word boundary
\B          not word boundary
\<          start of word
\>          end of word
```

## Matching Characters

```
.           any character except newline
[abc]       any of these characters
[^abc]      none of these characters
[a-z]       any character in this range
[*a-z]      not a character in this range
\d  \D      any digit / any character except a digit
\w  \W      any word / any character except a word
\s  \S      any white space / any character except white space
\c          any control character
\x          any hexadecimal digit
\O          any octal digit
\n          matches newline
\r          matches carriage return
\t          matches tab
\v          matches vertical tab
\f          matches form feed
\xxx        matches octal character xxx
\xhh        matches hex character hh
```

## Matching Words

```
ab?c        matches zero or one time, e.g. abc, ab7c
ab*c        matches zero or more times, e.g. abc, ab123c
a{3}        matches n times exactly, e.g. aaa
a{3,5}      matches from n to m times, e.g. aaa, aaaa, aaaaa
a{n,}       matches at least n times
abc|def     matches abc or def
```

