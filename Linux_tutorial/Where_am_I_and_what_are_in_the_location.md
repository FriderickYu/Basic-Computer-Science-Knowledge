# Where am I and what are in the location

## pwd: Where am I

`pwd`: print working directory, shows where you are now

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ pwd
/home/ytq
```

## ls: What are in the location

`ls`: list, what are in this current location

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq      模板  文档  桌面
idea.desktop      PycharmProjects  ytq.txt  视频  下载
IdeaProjects      snap             公共的   图片  音乐
```

`ls [options][location]`

`ls -l`: show what are in this current location, and their detailed information

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -l
总用量 68
-rw-r--r-- 1 ytq ytq 8980 4月  13  2022 examples.desktop
-rwxrw-r-- 1 ytq ytq  228 4月  29  2022 idea.desktop
drwxr-xr-x 3 ytq ytq 4096 4月  16  2022 IdeaProjects
drwxrwxr-x 4 ytq ytq 4096 2月   9 14:08 Linux-Tutorial
drwxrwxr-x 3 ytq ytq 4096 5月   2  2022 PycharmProjects
drwx------ 3 ytq ytq 4096 4月  16  2022 snap
```

* **First character** indicates whether it is a normal file *(-)* or directory *(d)*
* **Next 9 characters** are *permissions* for the file or directory
* The next field is the number of blocks
* The next field is the owner of the file or directory
* The next field is the group the file or directory belongs to
* The next field is the file size
* Next is the last file modification time
* Next is the actual name of the file or directory

`ls [location]`: list not current directory but instead to list locations' contents

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -l Linux-Tutorial/
总用量 12
-rw-rw-r-- 1 ytq ytq  431 2月   9 14:20 Linux_tutorial.md
drwxrwxr-x 2 ytq ytq 4096 2月   9 00:32 pictures
-rw-rw-r-- 1 ytq ytq   16 2月   9 00:30 README.md
```

## Path

Absolute paths specify a location (file or directory) in relation to **the root directory**. You can identify them easily as they always begin with a forward slash ( **/** )

Relative paths specify a location (file or directory) in relation to **where we currently are** in the system. They will not begin with a slash.

`~`: home directory

`.`: current directory

`..`: the parent directory