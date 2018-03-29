## git安装

- 官网

    [https://git-scm.com/](https://git-scm.com/)

- 下载

    [https://git-scm.com/download](https://git-scm.com/download)

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
    1. 创建SSH Key
    ssh-keygen -t rsa -C 'webwangxiong@163.com'

    用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，
    这两个就是SSH Key的秘钥对，id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人

    2.管理github
    登陆GitHub，打开“Account settings”，“SSH Keys”页面：
    然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：

    3.点“Add Key”，你就应该看到已经添加的Key：

    - 测试：ssh -T git@github.com  看是否缺少公钥

    注： id_rsa.pub文件位置：C:\Users\#{电脑名称}\.ssh
```

- 关联远程仓库
```
    git remote add origin git@github.com:<github账户名称>/<github仓库名称>
                                         <github账户名称>/<github仓库名称>	// github仓库的SSH地址
```

-- SSH与https两种地址的区别
```
    https://github.com/michaelliao/gitskills.git这样的地址。
    实际上，Git支持多种协议，默认的git://使用ssh，但也可以使用https等其他协议。
    使用https除了速度慢以外，还有个最大的麻烦是每次推送都必须输入口令，
    但是在某些只开放http端口的公司内部就无法使用ssh协议而只能用https。
```