# Move and File

## cd: Move to certain location

`cd [location]`: move to the certain location

if only `cd` without `location`, it will take you back to home directory

## Files

If you look at a file, in the end it is always an extension followed, like:

* file**.exe**: an executable file, or program
* file.**txt**: a plain text file
* file.**png**: an image

But in Linux, it's quite different. Linux ignores the extension, and looks inside the file to determine what type of file it is. So *myself.png* actually could be a text file rather than image to me.

`file [path]`: find out what exactly the file is

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ file Linux-Tutorial/Linux_tutorial.md
Linux-Tutorial/Linux_tutorial.md: UTF-8 Unicode text
```

Windows are case insensitive, but Linux is not. Like when we have two or mor files and directories with the same name but letters of different case. Linux sees these all as distinct and separate files.

### Hidden Files and Directories

`ls -a`: shows all files and directories, including hidden

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls -a
.              .config           .local                     ytq
..             .dbus             .mozilla                   ytq.txt
.android       examples.desktop  .pki                       .zoom
.ansible       .gconf            .profile                   公共的
.anyconnect    .gnupg            PycharmProjects            模板
.bash_history  .gvfs             .rpmdb                     视频
.bash_logout   .ICEauthority     snap                       图片
.bashrc        idea.desktop      .ssh                       文档
.bashrc.swp    IdeaProjects      .sudo_as_admin_successful  下载
.cache         .java             .thunderbird               音乐
.cisco         Linux-Tutorial    .viminfo                   桌面
```

Files and directories start with **.** , mean they are hidden.