在linux下查看进程大家都会想到用 ps -ef|grep XXX
可是看到的不是全路径，怎么看全路径呢？
每个进程启动之后在 /proc下面有一个于pid对应的路径
例如：ps -ef|grep python
显示：oracle    4431  4366  0 18:56 pts/2    00:00:00 python Server.py
4431就是进程号
到/proc/4431下，ls -l 会看到：
总用量 0
-r--r--r--    1 oracle   oinstall        0 12月 29 18:58 cmdline
lrwxrwxrwx    1 oracle   oinstall        0 12月 29 18:58 cwd -> /XXX/ultserver_aa
-r--------    1 oracle   oinstall        0 12月 29 18:58 environ
lrwxrwxrwx    1 oracle   oinstall        0 12月 29 18:58 exe -> /usr/bin/python2.4
dr-x------    2 oracle   oinstall        0 12月 29 18:58 fd
-r--------    1 oracle   oinstall        0 12月 29 18:58 maps
-rw-------    1 oracle   oinstall        0 12月 29 18:58 mem
-r--r--r--    1 oracle   oinstall        0 12月 29 18:58 mounts
lrwxrwxrwx    1 oracle   oinstall        0 12月 29 18:58 root -> /
-r--r--r--    1 oracle   oinstall        0 12月 29 18:58 stat
-r--r--r--    1 oracle   oinstall        0 12月 29 18:58 statm
-r--r--r--    1 oracle   oinstall        0 12月 29 18:58 status
注意cwd，即是你要查找的进程所在路径
