# Grep and Regular Expressions

## eGrep

`eGrep` will search a given set of data and print every line which contains a given pattern. 

`egrep [command line options] <pattern>  [path]`

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ egrep  'mellon' mysampledata.txt
Mark watermellons 12
Oliver rockmellons 2
```

`egrep -n` : know not only which lines matches but their line number as well.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ egrep -n 'mellon' mysampledata.txt
3:Mark watermellons 12
11:Oliver rockmellons 2
```

`egrep -c` : wish to know how many lines did match.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ egrep -c 'mellon' mysampledata.txt
2
```

