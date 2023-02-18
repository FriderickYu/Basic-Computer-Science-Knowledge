# Filter

## head

`head [-number of lines to print][path]` : prints first lines of it's input. By default of will print **the first 10 lines**.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ head mysampledata.txt 
Fred apples 20
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ head -2 mysampledata.txt 
Fred apples 20
Susy oranges 5
```

`head -2 mysampledata.txt` : means to show the first two lines of `mysampledata.txt`

## tail

`tail [-number of lines to print][path]` : `tail` is exact opposite of `head`, prints the last lines of it's input. By default of will print **the last 10 lines**.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ tail -5 mysampledata.txt 
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
```

## sort

`sort [-options][path]` : sort it's input, nice and simple. By default it will sort **alphabetically**. 

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ sort mysampledata.txt 
Anne mangoes 7
Betty limes 14
Fred apples 20
Greg pineapples 3
Lisa peaches 7
Mark grapes 39
Mark watermellons 12
Oliver rockmellons 2
Robert pears 4
Susy oranges 12
Susy oranges 5
Terry oranges 9
```

## nl

`nl [-options][path]` :stands for number lines.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ nl mysampledata.txt 
     1	Fred apples 20
     2	Susy oranges 5
     3	Mark watermellons 12
     4	Robert pears 4
     5	Terry oranges 9
     6	Lisa peaches 7
     7	Susy oranges 12
     8	Mark grapes 39
     9	Anne mangoes 7
    10	Greg pineapples 3
    11	Oliver rockmellons 2
    12	Betty limes 14
```

## wc

`wc [-options][path]` : stands for **word count**.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ wc mysampledata.txt 
 12  36 197 mysampledata.txt
```

If we use default module, the output will consist three numbers, representing newline, word and byte counts.

`wc -l` : shows lines only.

`wc -w` : shows words only.

`wc -m` : shows byte only. 

These options can be combined together, like `wc -lw`, means show lines and words altogether.

## cut

`cut [-options][path]` : to cut certain fields if the content is separated into columns.

We know that in `mysampledata.txt`, there are three columns, name, fruit and number.

## sed

`sed <expression> [path]` : stands for **Stream Editor** and allows us to do a search and replace on our data.

`s/search/replace/g` :

* `s` : stands for substiute and specifies the action to perform.
* `search` : what we want to search.
* `replace` : what we want to replace.
* `g` : global, it is optiona, if we ignore it, then it will just replace the first instance if **search**. If not then replacing every instance.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ head -12 mysampledata.txt 
Fred apples 20
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ sed 's/oranges/bananas/g' mysampledata.txt 
Fred apples 20
Susy bananas 5
Mark watermellons 12
Robert pears 4
Terry bananas 9
Lisa peaches 7
Susy bananas 12
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
```



## uniq

`uniq [options][path]` : stands for **unique**, removes duplicate lines from the data. But it only removes these duplicate lines which are adjacent.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cat mysampledata2.txt 
Fred apples 20
Susy oranges 5
Susy oranges 5
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ uniq mysampledata2.txt 
Fred apples 20
Susy oranges 5
Mark watermellons 12
Robert pears 4
Terry oranges 9
Lisa peaches 7
Susy oranges 12
Mark grapes 39
Anne mangoes 7
Greg pineapples 3
Oliver rockmellons 2
Betty limes 14
```

## tac

`tac [path]`  : quite opposite of `cat`, it shows the file reversely, from the end to start

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ tac mysampledata.txt 
Betty limes 14
Oliver rockmellons 2
Greg pineapples 3
Anne mangoes 7
Mark grapes 39
Susy oranges 12
Lisa peaches 7
Terry oranges 9
Robert pears 4
Mark watermellons 12
Susy oranges 5
Fred apples 20
```

