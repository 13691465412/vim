## 插件

### Vundle
用于安装其他vim插件的插件，需要手动安装，其他的通过它来安装就可以了，类似于Python中的pip。

+ 安装  
  首先从git下载(默认已经安装了git并且能够访问`github.com`):
  > git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim

  若是提示目录不存在则创建目录`/.vim/bundle/`  
  > cd ~  
  mkdir .vim  
  cd .vim  
  mkdir bundle  

+ 配置
  + 新建或者修改`.vimrc`文件
  + 在用户根目录下新建`.vimrc`文件。首先`cd ~`(切换到当前用户的根目录),然后使用`ls -al`查看是否有`.vimrc`,没有则使用`touch .vimrc`新建
  + 在`.vimrc`中添加以下配置
  ```
  set nocompatible
  filetype off
  set rtp+=~/.vim/bundle/Vundle.vim
  call vundle#begin()
  Plugin 'VundleVim/Vundle.vim'
  Plugin '你的插件' "这是要安装的插件的示例"
  call vundle#end()
  filetype plugin indent on
  ```
  + 保存并退出就可以了
+ 使用
  + 打开`.vimrc`, 添加要安装的vim插件
  ```
  "这是要安装的插件"
  Plugin 'scrooloose/nerdtree'
  ```
  + 保存`.vimrc`后再次打开，输入`:PluginInstall`就会进行安装，等到出现`Done!`代表所有插件安装完成.


## Anaconda使用
我们在对vim进行了一系列配置之后，却发现可能不能对python的第三方包进行提示，或者我们安装了anaconda，但是无法提示。

在`.bashrc`中加入以下配置：
```
# anaconda3 python PATH
export PYTHONPATH=/home/username/anaconda3/lib/python3.5/site-packages   
```