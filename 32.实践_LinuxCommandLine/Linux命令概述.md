## Linux命令概述



1. 命令使用方法

   - Linux命令格式:

       command  [-options][parameter1]  …

   ​

2. 查看帮助文档

   1. --help

      如：ls —help  这个命令没有什么用.

      ```bash
      [root@iz2ze9wve43n2nyuvmsfx5z ~]# ls --help
      Usage: ls [OPTION]... [FILE]...
      List information about the FILEs (the current directory by default).
      Sort entries alphabetically if none of -cftuvSUX nor --sort is specified.
      ```

   2. man

      如：man ls

      - man - an interface to the on-line **reference manuals**
      - 这是Linux最常用的查询命令.



3. 自动补全：

   在敲出命令的前几个字母的同时，按下tab键，系统会自动补全命令。

   ​

4. 历史命令：

   当系统执行过一些命令后，可按上下键翻看以前的命令，将执行过的命令列举出来。

   ```python
   [root@iz2ze9wve43n2nyuvmsfx5z ~]# history
       1  bash --version
       2  list
       3  ls
       4  printenv
       5  ls /
   ```

   ​

   ​

## Linux命令-文件、磁盘管理



1. 文件管理: `ls`

   ```python
   [root@iz2ze9wve43n2nyuvmsfx5z /]# ls
   bin   dev  home  lib64       media  opt   root  sbin  sys  usr
   boot  etc  lib   lost+found  mnt    proc  run   srv   tmp  var

   ```


2. 输出重定向命令：`>`

   ```python
   [root@iz2ze9wve43n2nyuvmsfx5z /]# ls > root_directories.md 
   # > 将结果输出到文件 root_directories.md 
   #查看 root_directories.md 文件
   [root@iz2ze9wve43n2nyuvmsfx5z /]# cat root_directories.md
   bin
   boot
   dev
   etc
   home
   lib
   lib64
   lost+found
   media
   mnt
   opt
   proc
   root
   root_directories.md
   run
   sbin
   srv
   sys
   tmp
   usr
   var
   ```


3. 分屏显示：more 这个命令被废弃了,常用`less`, less is more

   ​


4. 管道：`|`

   ```python
   #列出全部文件夹并标注数目
   [root@iz2ze9wve43n2nyuvmsfx5z /]# ls | nl
        1	bin
        2	boot
        3	dev
        4	etc
        5	home
        6	lib
        7	lib64
        8	lost+found
        9	media
       10	mnt
       11	opt
       12	proc
       13	root
       14	root_directories.md
       15	run
       16	sbin
       17	srv
       18	sys
       19	tmp
       20	usr
       21	var
   ```

   ​


5. 清屏：`clear`



6. 切换工作目录： `cd`



7. 显示当前路径：`pwd`



8. 创建目录：`mkdir`



9. 删除目录：`rmdir`



10. 删除文件：`rm`    注：rm 命令删除后不能恢复



11. 建立链接文件：`ln`



12. 查看或者合并文件内容：`cat`



13. 文本搜索：`grep`



14. 查找文件：`find`



15. 拷贝文件：`cp`



16. 移动文件：`mv`



17. 归档管理：`tar`



18. 文件压缩解压：`gzip`



19. 文件压缩解压：`bzip2`



20. 文件压缩解压：`zip`、`unzip`



21. 查看命令位置：`which`





##Linux命令-系统管理



1. 查看当前日历：cal

   ```python
   [root@iz2ze9wve43n2nyuvmsfx5z /]# cal
         June 2018     
   Su Mo Tu We Th Fr Sa
                   1  2
    3  4  5  6  7  8  9
   10 11 12 13 14 15 16
   17 18 19 20 21 22 23
   24 25 26 27 28 29 30
   ```

   ​


2. 显示或设置时间：date

    ```
    [root@iz2ze9wve43n2nyuvmsfx5z /]# date
    Mon Jun 18 13:23:32 CST 2018
    ```



3. 查看进程信息：ps



4. 动态显示进程：top



5. 终止进程：kill



6. 关机重启：reboot、shutdown、init



7. 检测磁盘空间：df



8. 检测目录所占磁盘空间：du



9. 查看或配置网卡信息：ifconfig



10. 测试远程主机连通性：ping







