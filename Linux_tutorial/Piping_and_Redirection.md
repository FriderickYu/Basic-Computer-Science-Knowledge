# Piping and Redirection

Every program has three data streams connected to it.

![stream](pic/streams.png)

1. `STDIN(0)` : standard input
2. `STDOUT(1)` : standard output
3. `STDERR(2)` : standard error

Piping and redirection is the means by which we may connect these streams between programs and files to direct data.

## Redirecting to a File

Sometimes we may wish to save it into a file to keep as a record.

`>` : indicates to the command line that we wish the programs ouput (or whatever it sends to STDOUT) to be saved in a file instead of printed to the screen.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls demo
mysampledata2.txt  mysampledata.txt
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls > myoutput
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ls
demo                                  Linux-Tutorial     ytq     下载
demo1                                 myoutput           公共的  音乐
examples.desktop                      mysampledata2.txt  模板    桌面
GitHubDesktop-linux-3.1.1-linux1.deb  mysampledata.txt   视频
idea.desktop                          PycharmProjects    图片
IdeaProjects                          snap               文档
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cat my
myoutput           mysampledata2.txt  mysampledata.txt   
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ cat myoutput
demo
demo1
examples.desktop
GitHubDesktop-linux-3.1.1-linux1.deb
idea.desktop
IdeaProjects
Linux-Tutorial
myoutput
mysampledata2.txt
mysampledata.txt
PycharmProjects
snap
ytq
公共的
模板
视频
图片
文档
下载
音乐
桌面
```

