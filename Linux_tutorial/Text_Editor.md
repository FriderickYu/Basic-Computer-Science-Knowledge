# Text Editor

There are two modes, **Insert** mode and **Edit** mode.

In insert mode, you can input or enter content.

In edit mode, you can move around this file, perform actions such as deleting, copying, search and replace, saving etc.

`vi <file>`

`ZZ`: Save and exit

`:q!`: discard all changes and exit

`:w`: save file but don't exit

`:wq`: again, save and exit

***Note***: Any command beginning with `:` requires you to hit `<enter>` to complete the command

## Other ways to view files

`cat <file>`: view files

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/Linux-Tutorial$ cat catalog.md 
# Catalog 

[Where am I and what are in the location](Where_am_I_and_what_are_in_the_location)

[Move and File](Move_and_File)

[Help](Help)

[File Manipulation](File_Manipulation)
```

But this command is more suitable when the file is relatvely small.

`less <file>`: to view a large file

`:set nu`: type in edit mode, will enable line numbers

## Undoing

`u`: undo the last action, if you keep pressing u, it will keep undo

`U`: undo all changes to the current line

[Vi cheatsheet](https://ryanstutorials.net/linuxtutorial/cheatsheetvi.php)