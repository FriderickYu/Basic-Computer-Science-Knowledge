





# File Manipulation

## Create directory

`mkdir [options] <Directory>`: making a directory

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq      模板  文档  桌面
idea.desktop      PycharmProjects  ytq.txt  视频  下载
IdeaProjects      snap             公共的   图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir experiment
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     snap     公共的  图片  音乐
experiment        Linux-Tutorial   ytq      模板    文档  桌面
idea.desktop      PycharmProjects  ytq.txt  视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir Linux-Tutorial/test
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls Linux-Tutorial/
Linux_tutorial.md  pictures  README.md  test
```

`mkdir -p <Directory>`: no error if existing, but if there is no such parent directories, creating a new parent directory

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     qty   ytq      模板  文档  桌面
experiment        Linux-Tutorial   snap  ytq.txt  视频  下载
idea.desktop      PycharmProjects  test  公共的   图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir fredrick/test
mkdir: 无法创建目录"fredrick/test": 没有那个文件或目录
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -p fredrick/test
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  idea.desktop    PycharmProjects  test     公共的  图片  音乐
experiment        IdeaProjects    qty              ytq      模板    文档  桌面
fredrick          Linux-Tutorial  snap             ytq.txt  视频    下载
```

`mkdir -v <Directory>`: when making directories, telling us what it is doing

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  idea.desktop    PycharmProjects  test     公共的  图片  音乐
experiment        IdeaProjects    qty              ytq      模板    文档  桌面
fredrick          Linux-Tutorial  snap             ytq.txt  视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -pv test2
mkdir: 已创建目录 'test2'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -pv fredrick/test3
mkdir: 已创建目录 'fredrick/test3'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mkdir -v test3
mkdir: 已创建目录 'test3'
```

## Delete directory

`rmdir [options] <Directory>`: remove the directory

`rmdir -p <Directory>` and `rmdir -pv <Directory>` and `rmdir -v <Directory>` are very similar with `mkdir [options] <Directory>` 

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     snap   ytq      视频  音乐
experiment        Linux-Tutorial   test   ytq.txt  图片  桌面
fredrick          PycharmProjects  test2  公共的   文档
idea.desktop      qty              test3  模板     下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir qty
rmdir: 删除 'qty' 失败: 目录非空
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir experiment/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  IdeaProjects     qty   test2  ytq.txt  视频  下载
fredrick          Linux-Tutorial   snap  test3  公共的   图片  音乐
idea.desktop      PycharmProjects  test  ytq    模板     文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir -pv fredrick/test2
rmdir: 正在删除目录 'fredrick/test2'
rmdir: 删除 'fredrick/test2' 失败: 没有那个文件或目录
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls fredrick/
test  test3
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir -pv fredrick/test
rmdir: 正在删除目录 'fredrick/test'
rmdir: 正在删除目录 'fredrick'
rmdir: 删除目录 'fredrick' 失败: 目录非空
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cd fredrick/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/fredrick$ rmdir test
rmdir: 删除 'test' 失败: 没有那个文件或目录
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/fredrick$ cd ..
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rmdir -pv fredrick/test3/
rmdir: 正在删除目录 'fredrick/test3/'
rmdir: 正在删除目录 'fredrick'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   snap   test3    公共的  图片  音乐
idea.desktop      PycharmProjects  test   ytq      模板    文档  桌面
IdeaProjects      qty              test2  ytq.txt  视频    下载
```

If the directory we want to delete is not empty, we can't delete this directly.

## Create a blank file

`touch [options] <filesname>`: create a blank file

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   snap     公共的  图片  音乐
idea.desktop      PycharmProjects  ytq      模板    文档  桌面
IdeaProjects      qty              ytq.txt  视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ touch test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   snap      ytq.txt  视频  下载
idea.desktop      PycharmProjects  test.txt  公共的   图片  音乐
IdeaProjects      qty              ytq       模板     文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ file test.txt 
test.txt: empty
```

## Copy a File or Directory

`cp [options] <source> <destination>`: copy a file or directory to the destination.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq.txt   视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp test.txt ytq
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq/
test.txt
```

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq.txt   视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp test.txt ytq/ytq1/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq/ytq1/
test.txt
```

`cp -r <source> <destination>`: copy directories or files

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  模板  文档  桌面
idea.desktop      PycharmProjects  ytq       视频  下载
IdeaProjects      snap             公共的    图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp -r ytq Linux-Tutorial/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cd Linux-Tutorial/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~/Linux-Tutorial$ ls
Linux_tutorial.md  pictures  README.md  test  ytq
```

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp ytq2 ytq
cp: -r not specified; omitting directory 'ytq2'
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cp -r ytq2 ytq
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq2    视频  下载
IdeaProjects      snap             公共的  图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq/
test.txt  ytq1  ytq2
```

## Move a file or directory

`mv [options] <source> <destination>`: move a file or directory to the destination

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  模板  文档  桌面
idea.desktop      PycharmProjects  ytq       视频  下载
IdeaProjects      snap             公共的    图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mv test.txt Linux-Tutorial/
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     视频  下载
idea.desktop      PycharmProjects  公共的  图片  音乐
IdeaProjects      snap             模板    文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls Linux-Tutorial/
Linux_tutorial.md  pictures  README.md  test  test.txt  ytq
```

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq2    视频  下载
IdeaProjects      snap             公共的  图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mv ytq2 ytq
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     视频  下载
idea.desktop      PycharmProjects  公共的  图片  音乐
IdeaProjects      snap             模板    文档  桌面
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls ytq
test.txt  ytq1  ytq2
```

`mv` can also rename files and directories

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq2    视频  下载
IdeaProjects      snap             公共的  图片  音乐
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ mv ytq2 ytq3
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq3    视频  下载
IdeaProjects      snap             公共的  图片  音乐
```

## Remove a file (and not empty directories)

`rm [options] <file>`: remove a file

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq3      视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rm test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq3    视频  下载
IdeaProjects      snap             公共的  图片  音乐
```

`rm -r <non empty Directories>`: remove a non empty directories

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   test.txt  公共的  图片  音乐
idea.desktop      PycharmProjects  ytq       模板    文档  桌面
IdeaProjects      snap             ytq3      视频    下载
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ rm test.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
examples.desktop  Linux-Tutorial   ytq     模板  文档  桌面
idea.desktop      PycharmProjects  ytq3    视频  下载
IdeaProjects      snap             公共的  图片  音乐
```
