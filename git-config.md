# Git 配置
> 多一个选项，多一层变量。

## Contents / Mind mapping
- **1 配置分级**
  - **1-1 系统级**
  - **1-2 用户级**
  - **1-3 仓库级**
- **2 查看配置**
- **3 配置选项**
  - **3-1 用户信息**
  - **3-2 编辑器**

---

### 1 配置分级

配置文件分为三个等级：系统级（--system）、用户级（--global）、仓库级（--local）。三者的生效原则为：仓库级 > 用户级 > 系统级。

#### 1-1 系统级

系统级配置文件为`/etc/gitconfig`，该配置文件对系统中所有仓库有效，可以使用如下命令来进行设置：
```
git config --system <key> <value>
```

#### 1-2 用户级

用户级配置文件为`~/.gitconfig`，该配置文件对该用户的所有仓库有效，可以使用如下命令来进行设置：
```
git config --global <key> <value>
```

#### 1-3 仓库级

仓库级配置文件是每个仓库下`.git/config`，该文件仅对当前仓库有效，可以使用如下命令来进行设置：
```
git config --local <key> <value>
```



### 2 查看配置

如果想要检查你的配置，可以使用 `git config --list` 命令来列出所有 Git 当时能找到的配置。

也可以通过输入 `git config <key>` 来检查 Git 的某一项配置。



### 3 配置选项

安装完 Git 后的第一件事情就是配置用户名、邮箱和编辑器。

#### 3-1 用户信息 

配置 Git 的第一步就是配置用户的名字和邮箱，由于后续每一个 Git 的提交都需要用到用户名和邮箱，所以这一步必不可少：
```
$ git config --global user.name <name>
$ git config --global user.email <email addr>
```

#### 3-2 编辑器

当 Git 需要你输入信息的时候，会调用系统的默认编辑器，如果你想使用自己喜欢的编辑器，就通过以下配置来实现：
```
$ git config --global core.editor <editor name>
```

#### 3-3 命令别名

可以通过以下配置来简化命令行输入，让 Git 用起来更加方便：
```
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
git config --global alias.ci commit
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```
