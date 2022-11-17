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
我们的服务器并没有连接外网，因此当我们需要下载一些特定的程序或软件包，或从本地和服务器之间进行文件传输的时候，sftp会是一个很好用的工具  
同ssh一样，我们可以通过sftp连接本地和服务器，这种连接可以完成快速的文件传输操作而不能实现运行程序等其他操作  
1. 登陆sftp  
> sftp username@server  
> password(invisible)  

2. 上传文件或文件夹至服务器  
> put /local_file_path /server_target_path  #上传文件  
> put -r /local_folder_path/ /server_target_path  #上传文件夹内的文件  


2. 下载文件或文件夹至本地  
> get /server_file_path /local_target_path  #下载文件  
> get -r /server_folder_path/ /local_target_path  #下载文件夹内的文件  
## conda  

conda为我们提供了一个环境，每一个环境安装了不同的安装包，以满足不同程序运行的需要。例如当一个程序运行时需要A版本的软件1，另外一个程序运行时需要B版本的软件1，假如我们没有版本控制的环境的话，我们需要在我们的原始环境中不断地安装、删除软件，以满足不同程序的需要，conda正是解决了这个问题。  

### conda的下载和安装  
#### 下载anaconda
进入下面这个网址查看conda的版本    
https://repo.anaconda.com/archive/  

下载方法一：在本地下载并上传至服务器  
在刚刚的网站上面选择适配服务器的anaconda(一般是对应于linux Ubuntu系统的最新版本)  
利用sftp上传至服务器  

下载方法二：直接在服务器上下载  
首先我们需要在刚刚的网址找到我们需要下载的anaconda的版本号，然后直接连接服务器并在服务器的命令行上输入  
> wget https://repo.anaconda.com/archive/Anaconda3-5.3.0-Linux-x86_64.sh

上面指令中的anaconda的版本号需要我们替换成我们需要的版本号  
当我们遇到wget指令无法识别的问题时(一般不会遇到这个问题，因为其他同学已经下载过了)，输入以下指令下载wget即可  
> apt-get install -y wget

#### 安装anaconda  
首先修改anaconda的权限(chomd命令可以修改文件的权限，如果同学们未来需要修改文件权限时自行查询即可，这里不做过多的讲解)  
> chmod +x Anaconda3-5.3.0-Linux-x86_64.sh  

然后运行anaconda的脚本文件  
> sh Anaconda3-5.3.0-Linux-x86_64.sh  

按照提示走完安装流程即可  
两次需要选择yes or no的部分均选择yes  

如果不小心选择了no可以按照这一篇blog中的方法，用编辑器vim或者vi进入到bash的环境变量中将conda手动添加进去  
https://blog.csdn.net/wyf2017/article/details/118676765  

### 利用anaconda创建虚拟环境  
1. 创建环境  
在命令行输入以下命令创建虚拟环境，需要将你自己的环境的名称和python的版本号进行相应的替换  
> conda create -n your_env_name python=your_python_version  

2. 激活环境
当我们有了创建好的环境之后，我们可以通过以下指令查看我们已经存在的环境，其中base环境是我们每次进入bash的时候的初始环境  
> conda info --envs

每次我们需要进入到某个环境中去的时候需要激活该环境，这时候我们就从base转入到该环境中去了  
> conda activate your_env_name  

当我们需要切换环境或者回到初始环境的时候，我们需要接触激活状态  
> conda deactivate  

### 下载安装包
我们举出下载pytorch的例子来展示我们如何在特定的环境中安装我们想要的软件包  
首先我们激活想要安装的环境，这个环境应当被提前下载好  

> conda activate your_env_name  

查看当前服务器(或者个人电脑cuda对应的版本)  
> nvidia-smi  

记住左上角的版本号，一会儿需要按照这个版本号进行下载对应的pytorch版本！！！  
进入下面的网站选择合适的pytorch版本，下载器选择conda，复制命令并输入到激活了conda环境的命令行即可完成下载  
 > https://pytorch.org/
 

## CUDA & CPU 
查看GPU版本和占用情况：  
> nvidia-smi  

查看CPU版本和占用情况：
> top  

查看内存使用情况：
> free  

