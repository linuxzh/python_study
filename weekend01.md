## 开发环境的准备
我们需要不去更改Linux系统默认提供的包，如进行更改的话，将会打乱Linux里面的Python，通常在开发的时候都会搭建一个专门用于开发的Python环境。

### pyenv
* 安装Python解析器
* 管理Python版本
* 通过插件可管理Python虚拟环境（相当于一个独立的版本）

pyenv 地址：https://github.com/yyuu/pyenv

`pyenv-installer`：用于安装pyenv的程序   
地址：https://github.com/yyuu/pyenv-installer

安装`pyenv-installer`:
```
curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer | bash
```
配置环境变量，在用户的家目录中的`~/.basr_profile`
```
export PATH="~/.pyenv/bin:$PATH"
eval "$(pyenv init -)"
eval "$(pyenv virtualenv-init -)"
```
在生产环境中如何安装pyenv的呢？
先sudo到root用户下：   
在安装前指定pyenv安装的路径，如`export PYENV_ROOT=/opt/pyenv`,然后在进行安装的。
```
curl -L https://raw.githubusercontent.com/yyuu/pyenv-installer/master/bin/pyenv-installer |  bash
```
环境变量，添加到`/etc/profile.d/`目录下，即可。

安装pyenv 编译所需要的依赖包：
```
yum install gcc make  patch gdbm-devel openssl-devel sqlite-devel zlib-devel bzip2-devel readline-devel -y
```

安装`pyenv` 的版本 3.5.2
```
pyevn install 3.5.2
```
查看能安装的版本：
```
pyevn install --list
```
