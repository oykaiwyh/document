### Linux

#### 分区

- /boot   linux启动的引导文件200m
- 





### Linux命令

| 命令                                                         | 说明                                      |
| ------------------------------------------------------------ | ----------------------------------------- |
| touch aa.txt/aa.md/aa                                        | 建立一个文件aa.txt/aa.md                  |
| yy                                                           | vim正常模式下复制当前行                   |
| dd                                                           | vim正常模式下删除当前行                   |
| :set nu                                                      | vim 命令模式下设置行号                    |
| :set nonu                                                    | vim 命令模式下不显示行号                  |
| /关键字   输n找到下一个匹配项                                | vim 命令行模式下查找                      |
| gg                                                           | vim正常模式下回到首行                     |
| G                                                            | vim正常模式下回到末尾                     |
| u                                                            | vim正常模式下撤销编辑模式所做的上一个修改 |
|                                                              |                                           |
| gzip                                                         | 压缩文件，不保留源文件                    |
| gunzip                                                       | 解压文件，不保留源文件                    |
| zip 选项  压缩名xxx.zip 压缩内容<br />       选项：-r：递归压缩，即整个目录 | 压缩文件，保留源文件un                    |
| unzip 选项 解压路径 压缩名xxx.zip <br />       选项：-d：解压缩，存放的路径 | 解压缩文件，保留源文件                    |
| tar 选项 合并名称xx.tar.gz  文件a 文件b <br />       选项：-zcvf：打包 | tar指令打包                               |
| tar 选项 合并名称xx.tar.gz  文件a 路径 <br />       选项：-zcvf：打包 | tar指令打包一个文件                       |
| tar 选项 解压名称xx.tar.gz   <br />       选项：-zxvf：解压  | tar指令解压                               |
| tar 选项 解压名称xx.tar.gz  -C 指定目录（必须存在）  <br />       选项：-zxvf：解压 | tar指令解压                               |
|                                                              |                                           |

### 其它

| 内容                      | shuom              |
| ------------------------- | ------------------ |
| ftp                       | 默认监听21号端口   |
| sftp                      | 默认监听22号端口   |
| /etc/profile              | 配置环境变量       |
| /etc/sysconfig/iptables   | 虚拟机配置端口放行 |
| telnet ip                 | 测试连接           |
| service iptables status   | 显示放行端口       |
| find / -name  'file name' | 以文件名查找文件   |
|                           |                    |
|                           |                    |

