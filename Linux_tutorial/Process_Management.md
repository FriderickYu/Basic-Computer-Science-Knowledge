# Process Management

A program is a series of instructions, tells the computer what to do. So when we run the program, these instructions are copied into memory. Space is allocated for variables. These running instance of program is called a process.

## top what is currently running?

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ top
top - 20:25:30 up  2:11,  1 user,  load average: 0.91, 0.89, 0.99
任务: 359 total,   2 running, 286 sleeping,   0 stopped,   0 zombie
%Cpu(s):  6.2 us,  1.9 sy,  0.0 ni, 90.8 id,  0.1 wa,  0.0 hi,  1.0 si,  0.0 st
KiB Mem :  7879824 total,   575628 free,  2746736 used,  4557460 buff/cache
KiB Swap:  2097148 total,  2097148 free,        0 used.  4270144 avail Mem 

process USER      PR  NI    VIRT    RES    share  %CPU %MEM     TIME+ COMMAND                                                                                                                                 
13295 ytq       20   0 28.791g 467104 142876 S  36.9  5.9  27:34.69 chrome                                                                                                                                  
 4005 root      20   0  365892  16876  14064 S  10.3  0.2   4:00.31 vpn                                                                                                                                     
 3239 ytq       20   0 1395232 112976  77472 R   6.0  1.4   3:16.65 Xorg                                                                                                                                    
 3434 ytq        9 -11 2647212  18564  14392 S   5.6  0.2   4:26.41 pulseaudio                                                                                                                              
15833 ytq       20   0  844068  50824  37960 S   4.0  0.6   0:09.78 gnome-terminal-                                                                                                                         
 3407 ytq       20   0 4435236 363892 138072 S   3.3  4.6   4:09.30 gnome-shell    
```

`top` shows a realtime view of the system and only shows the number of processes.

`ps` shows just the processes running in your current terminal. 

`ps [aux]`  : show a complete system.

```bash
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ps
  PID TTY          TIME CMD
15843 pts/0    00:00:00 bash
21591 pts/0    00:00:00 ps
ytq@ytq-Lenovo-XiaoXin-Air-13IML:~$ ps aux
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root         1  0.1  0.1 225932  9544 ?        Ss   18:14   0:13 /sbin/init splash
root         2  0.0  0.0      0     0 ?        S    18:14   0:00 [kthreadd]
root         3  0.0  0.0      0     0 ?        I<   18:14   0:00 [rcu_gp]
root         4  0.0  0.0      0     0 ?        I<   18:14   0:00 [rcu_par_gp]
root         6  0.0  0.0      0     0 ?        I<   18:14   0:00 [kworker/0:0H-kb]
root         8  0.0  0.0      0     0 ?        I<   18:14   0:00 [mm_percpu_wq]
```

## Killing a process

`kill [signal] <PID>` : kill process PID.

## Foreground and background  

Sometimes some processes are no need to run in the foreground, we will move these in the background to continue working. 

`sleep [time][process]`  : make which process sleep for a while.

 `fg <job number>`  : to bring background processes into the foreground.

