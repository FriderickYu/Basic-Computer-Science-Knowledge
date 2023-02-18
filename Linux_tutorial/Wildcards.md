# Wildcards

In the previous *FIle Manipulation*, it always operates on a single file at a time. It is not efficient way.

*Wildcards* are a set of building blocks that allow you to create a pattern defining a set of files or directories.

Basic set of wildcards:

* `*`: represents zero or more characters
* `?`: represents a single character
* `[]`: represents a range of characters

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls
experiment.txt  test1.txt  test2.txt  test.txt  ytq1  ytq2
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls t*
test1.txt  test2.txt  test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls *.txt
experiment.txt  test1.txt  test2.txt  test.txt
```

`*`: this is more like *pattern matching*. It replaces the pattern with every file or directory that matches the pattern

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls ?e*
test1.txt  test2.txt  test.txt
```

`[]`, the range operation allows to limit to a subset of character. In this example, we are looking for every file whose name either begins with *e* or *t*

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls [et]*
experiment.txt  test1.txt  test2.txt  test.txt
```

By using hyphen(-), we change include a set with range.

The next code shows, we want to search files, name begins with multiple letters, in the middle, the number is from 0-2, and ends with multiple letters.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls *[0-2]*
test1.txt  test2.txt

ytq1:
test.txt

ytq2:
```

caret(^) means look for any character which is not one of the following

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls [^a-g]*
test1.txt  test2.txt  test.txt

ytq1:
test.txt

ytq2:
```

