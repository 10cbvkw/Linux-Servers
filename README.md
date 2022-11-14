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
如果需要执行多个python程序(或者需要在命令行依次输入多条指令)，只需要编写一个sh脚本，然后运行即可,脚本会自动的依次执行你所提供的脚本文件中的每一行指令  
> sh xxx.sh

### pip
在运行程序或其他操作的时候，通常会涉及到调用一些已经存在的包，这些包需要从网上下载，而pip就是一个下载软件包的软件  
1. linux安装pip  
> wget https://bootstrap.pypa.io/get-pip.py  
> python get-pip.py  

conda环境中也可以安装pip，这在之后会提到  
2. pip 的使用  
我们可以通过在命令行键入pip和需要下载的安装包的名字来下载该安装包  
> pip install xxx

### vim
vim 是一个编辑器，当我们在linux中还未安装任何可视化的编辑器，但是需要编辑一些脚本文件时，我们可能会用到 vim  
我将会给大家提供一些vim最基本的常用操作以及两篇参考，帮助大家不同程度地了解 vim  
基本上 vim 共分为三种模式，分别是命令模式（Command mode），输入模式（Insert mode）和底线命令模式（Last line mode）
1. 启动 vim  
我们可以通过在命令行键入 vim 和需要打开的文件的名字来启动 vim  
> vim xxx  

2. 刚刚启动 vim 之后进入的就是命令模式，这时候我们无法对打开文件的内容进行修改，只能键入一些命令  
进入输入模式  
> i 

进入底线命令模式  
> ：

3. 进入命令模式之后我们可以正常的对内容进行编辑，在编辑完成之后我们可以通过按 esc 键返回命令模式  
4. 进入底线命令模式之后我们可以用一些简单的操作来保存文件  
退出  
> q  

保存并退出  
> wq  
参考1：https://github.com/vim/vim  
参考2：https://www.runoob.com/linux/linux-vim.html  
## sftp

## conda 

## CUDA & CPU

## git & github
