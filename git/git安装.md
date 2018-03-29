## git安装

- 官网
[https://git-scm.com/](https://git-scm.com/)

- 参考资料
[https://git-scm.com/book/zh/v2](https://git-scm.com/book/zh/v2)


```
每个用户的git配置文件：.gitconfig

git配置：.git/config
1.git config --global user.name ''
用户名

2.git config --global user.email ''
用户邮箱

3.git config --global color.ui true
显示颜色

4.git config --global alias.st status
配置别名 st 代替 status

git config --global alias.co checkout
co 代替 checkout

git config --global alias.ci commit
ci 代替 commit

git config --global alias.br branch
br 代替 branch

git config --global alias.unstage 'reset HEAD'
unstage 代替 reset HEAD

git config --global alias.last 'log -1'

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"

```

- 忽略特殊文件：

> .gitignore文件

配置文件
[https://github.com/github/gitignore](https://github.com/github/gitignore)
[http://www.gitignore.io](http://www.gitignore.io)

- 忽略文件的原则
    - 忽略操作系统自动生成的文件，比如缩略图等
    - 忽略编译生成的中间文件、可执行文件等，也就是如果一个文件是通过另一个文件自动生成的，那自动生成的文件就没必要放进版本库，比如Java编译产生的.class文件
    - 忽略你自己的带有敏感信息的配置文件，比如存放口令的配置文件


- 生成SSH Key
```
    ssh-keygen -t rsa -C 'webwangxiong@163.com'
```

- 关联远程仓库
```
    git remote add origin git@github.com:<github账户名称>/<github仓库名称>
                                         <github账户名称>/<github仓库名称>	// github仓库的SSH地址
```
