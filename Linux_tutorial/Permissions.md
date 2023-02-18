# Permissions

## 3 permissions

`r` : read - you can **view** the contents of the file.

`w` : write - you can **change** the contents of the file.

`x` : execute - you can **execute or run** the file if it is a program or script.

## 3 Sets of people

`owner` : a single person who owns the file.

`group` : every file belongs to a single group.

`others` : everyone else who is not in the group or the owner.

## View permissions for files

`ls -l <path>` : view permissions for a file.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -l ytq/
总用量 12
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 experiment.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test1.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test2.txt
-rw-rw-r-- 1 ytq ytq   38 2月  10 14:55 test.txt
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:00 ytq1
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:08 ytq2
```

* The first character identifies the file type. If it is a dash (*-*) then it is a normal file. If it is *d* then it is a directory --> `- file` or `d directory`.
* **Next 9 characters** are *permissions* for the file or directory.
  * The first following 3 characters show the permissions for the **owner**. Like `experiment.txt`, the owner has permissions of read and write, not execute.
  * The second following 3 characters show the permission for the **group**.
  * The last following 3 characters show the permission for **others**.

## Change permissions for files

`chmod [permissions] [path]` : change permissions on a file or directory

* Who are we changing? owner, group, others
* Are we granting or revoking the permission? +, -
* Which permission are we setting? r, w, x

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls -l
总用量 12
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 experiment.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test1.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test2.txt
-rw-rw-r-- 1 ytq ytq   38 2月  10 14:55 test.txt
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:00 ytq1
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:08 ytq2
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ chmod g+x experiment.txt 
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls -l
总用量 12
-rw-rwxr-- 1 ytq ytq    0 2月  10 15:33 experiment.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test1.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test2.txt
-rw-rw-r-- 1 ytq ytq   38 2月  10 14:55 test.txt
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:00 ytq1
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:08 ytq2
```

We can also assign multiple permissions for multiple roles at one time

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ chmod og+x experiment.txt 
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/ytq$ ls -l
总用量 12
-rw-rwxr-x 1 ytq ytq    0 2月  10 15:33 experiment.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test1.txt
-rw-rw-r-- 1 ytq ytq    0 2月  10 15:33 test2.txt
-rw-rw-r-- 1 ytq ytq   38 2月  10 14:55 test.txt
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:00 ytq1
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:08 ytq2
```

## Permissions Shorthand

Permission system is represented by octal system (0~7). Because there are 3 permissions and each being on or off, so there are $2^3$ combinations. 

| Octal | Binary |
| :---: | :----: |
|   0   | 0 0 0  |
|   1   | 0 0 1  |
|   2   | 0 1 0  |
|   3   | 0 1 1  |
|   4   | 1 0 0  |
|   5   | 1 0 1  |
|   6   | 1 1 0  |
|   7   | 1 1 1  |

This is more convenient, when compared it to r, w,d, o, g, etc.

Like `chmod 666 file`, means granting read and write permissions for all owner, group and others, but revoking execute permission for all roles.

##Permissions for directories

*A little bit different*

`r` : same as file, read the contents of the directory.

`w` : same as file, write into the directory.

`x` : different from file, enter the directory.

`ls -ld <directory>` : view the permissions for a specific directory.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -ld ytq/
drwxrwxr-x 4 ytq ytq 4096 2月  12 22:36 ytq/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -l ytq
总用量 12
-rwxrwxrwx 1 ytq ytq    0 2月  10 15:33 test1.txt
-rw-rw-r-- 1 ytq ytq   38 2月  10 14:55 test.txt
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:00 ytq1
drwxrwxr-x 2 ytq ytq 4096 2月   9 16:08 ytq2
```

