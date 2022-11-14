# Linux-Servers
this document contains basic operations on linux servers
这篇markdown的内容包括了使用linux服务器的一些基本操作

## Sign in

### Terminal
1. 终端进入方式：  
 - Linux Ctrl+Alt+T  
 - MAC 在应用程序里可以找到terminal  
 - Win 开始界面输入cmd  

2. 在命令行输入如下指令连接ssh：
> ssh username@server  
> password(invisible)  
### VScode
1. 打开VScode安装remote ssh插件   
2. 进入插件点击加号  
3. 按照scode的提示一次输入如下指令连接ssh：  
> ssh username@server  
> password(invisible)  

## Basic operation of linux
### path   
路径：  
- /绝对路径  
- 相对路径  
### shell
1. 显示当前目录下的文件和文件夹  
> ls  
2. 进入目录中的某个文件夹
> cd xxx                                        #进入文件夹  
> cd /path                                      #使用绝对路径进入文件夹   
> cd relative_path                              #使用相对路径进入文件夹    
> cd ..                                         #进入上层  
> cd -                                          #进入刚刚的目录  
3. 创建文件和文件夹  
> touch file  
> mkdir folder  
5. 复制文件
> cp file1 file2                                #复制文件1到文件2  
> cp file1 folder1                              #复制文件1到文件夹1  
> cp -r folder1 folder2                         #复制文件夹1的全部内容到文件夹2  
6. 移动文件  
> mv file1 file2                                #移动文件1到文件2  
> mv file1 folder1                              #移动文件1到文件夹1  
> mv -r folder1 folder2                         #移动文件夹1的全部内容到文件夹2
7. 删除文件  
> rm file                                       #删除文件  
> rm -r folder                                  #删除文件夹中全部文件  
8. 其他命令可以查看我在github上传的绍持提供的lecture_notes_closter.pdf  

### python
linux一般自带python，我们可以直接在命令行键入python即可进入命令行模式下的python  
> python

如果想运行自己写的python文件，只需要在命令行键入python再加上python文件的路径  
> python xxx.py  

### sh  


### pip

### vim

## sftp

## conda 

## CUDA & CPU

## git & github
