## git命令

- 参考资料
    - git常用命令
        [http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html](http://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html)

    - git工作流程
        [http://www.ruanyifeng.com/blog/2015/12/git-workflow.html](http://www.ruanyifeng.com/blog/2015/12/git-workflow.html)

- 初始化git仓库
```
    git init

    git init [project-name]     // 新建一个目录，将其初始化为Git代码库
```   

- 查看当前路径
```
    pwd
```  

- 查看当前目录下的所有文件夹（包括隐藏文件夹）
```
    ls -ah
    ls： 不包括隐藏文件夹
```

- 查看内容
```
    cat readme.txt
```

- 进入文件夹修正
```
    vi <file>
```

- 创建文件夹
``` 
    mkdir <file-name>
```

- 跳转到对应的路径
```
    cd + 路径
```

- clone一个git项目
```
    git clone https://github.com/wangxiong1004/document.git
    git clone git@github.com:<github账户名称>/<github仓库名称>
``` 

- 查看当前状态
```
    git status
```   

- 添加文件添加到本地暂存区
```
    git add -A	// 添加所有改动
    git add *	// 添加新建文件和修改，但是不包括删除
    git add .	// 添加新建文件和修改，但是不包括删除
    git add -u	// 添加修改和删除，但是不包括新建文件
```

- 加暂存区文件添加到本地仓库
```
    git commit -m '注释'
```

- 查看文件修改内容
```
    git diff + 文件
    git diff： 是工作区（work dict）和暂存区（stage）的比较
    git diff --cached ： 是暂存区（stage）和分支（master）的比较
```

- 查看工作区和版本库里面最新版本的区别
```
    git diff HEAD -- readme.txt
```

- 拉取远程分支代码
```
    git pull origin master
```  

- 查看从最近到最远的提交日志
```
    git log
    git log --pretty=oneline    // 一行展示
```

- 查看历史提交版本
```
    git reflog
```

- 回退到上一个版本
```
    git reset --hard HEAD^
    HEAD：当前版本
    HEAD^: 上一个版本
    HEAD^^: 上上个版本
    HEAD~100：回退到上100个版本
```

- 回退到指定版本
```
    git reset --hard + 版本号
```

- 撤销还没add的修改
```
    git checkout -- readme.txt
```

- 撤销已经add但还没commit的修改
```
    git reset HEAD <file>
```

- 删除本地文件
```
    rm <file>
    add且commit后的文件：删除本地文件，rm <file>
    一：执行删除
    git rm <file>
    从版本库中删除文件，执行后还要执行git commit -m '';
    二：删除错误，还原
    git checkout -- <file>
```

- 提交到远程仓库
```
    git push origin master
    git push -u origin master   // 第一次提交加参数-u
```

- 创建并切换到dev分支
```
    git checkout -b dev
    git branch dev		// 创建dev分支
    git checkout dev	// 切换到dev分支
```

- 查看当前分支及所有分支
```
    git branch  // 当前分支前标有一个*号
```

- 删除dev分支
```
    git branch -d dev
```

- 合并分支
```
    git merge dev   // fast forward 模式下，删除分支后，会丢掉分支信息
    git merge --no-ff -m 'merge with no-ff' dev	// 使用--no-ff参数合并分支，会创建一个新的commit，所以加上-m '提交描述'
```

- 查看分支的合并情况
```
    git log --graph --pretty=oneline --abbrev-commit
```

- 保存工作区的修改
```
    git stash
```

- 查看保存的内容
```
    git stash list
```

- 恢复缓存的内容
```
    git stash apply // stash内容并不删除，删除使用git stash drop
    git stash apply stash@{0}	// 恢复指定的stash
    git stash pop --index stash@{0}	// 恢复指定的stash

    git stash pop   // 恢复工作区的内容，并将stash内的内容删除	
```

- 删除stash的内容
```
    git stash clear
```

- 强行删除分支
```
    git branch -D wangxiong // // 如果分支还没有被合并，想要删除，使用git branch -d <name>无法完成操作，会报错，需要使用git branch -D <name>强行删除

    -- error: The branch 'name' id not fully merged.
    -- If you are sure you want to delete it,run 'git branch -D <name>'
```

- 查看远程库的信息
```
    git remote
    git remote -v 	// 查看更详细的信息
```

- 创建远程origin的dev分支到本地
```
    git checkout -b dev origin/dev
```

- 指定本地dev分支与远程origin/dev分支的链接
```
    git branch --set-upstream dev origin/dev
```

- 远程拉取最新代码
```
    git pull
```

- 创建标签
``` 
    git tag
``` 

- 给对应的提交打上标签	
```
    git tag v1.0 6224937    // 6224937：commit id
```

- 查看标签信息
```
    git show <tagname>
```

- 创建带有说明的标签
```
    git tag -a v1.0 -m 'version 1.0' 3628164    // -a: 指定标签名	-m: 指定说明文字    
```

- 通过-s用私钥签名一个标签
```
    git tag -s v2.0 -m 'signed version 2.0' fec45a  // 签名采用PGP签名。因此，必须首先安装gpg（GnuPG），如果没有找到gpg，或者没有gpg密钥对，就会报错
```

- 删除标签
```
    git tag -d v1.0     // 还没推送到远程的标签

    git push origin :refs/tags/v2.0     // 已经推送到远程的标签
```

- 推送某个标签到远程
``` 
    git push origin <tagname>

    git push origin --tags  // 推送全部尚未推送到远程的本地标签
```

- 强制添加被忽略的文件到git
```
    git add -g app.class
```

- 检查.gitignore文件，哪个规则写错了
```
    git check-ignore -v app.class
```

- 合并某个分支上的单个commit
```
    git cherry-pick <commit-id>
```

- 合并某个分支上的一系列commits
```
    git rebase --ontomaster 76cada^

    -- 先在这个分支上创建一个新的分支，并指明新分支的最后一个commit
    git checkout --bnewbranch 62ecb3
    -- 然后，rebase 这个分支的commit 到master（--ontomaster）. 76cada^指明想从哪个特定的commit开始
    git rebase --ontomaster 76csda^
```

- 清空远程分支
```
    git remote prune origin
```

- 删除git上的分支后，本地执行命令，清除本地分支
```
    git branch -D new_invite

    git remote prune origin
``` 

- 更新远程新分支
```
    git remote update origin --prune
```

- 查看git的命令目录地址
```
    git --exec-path
```

- 显示当前的Git配置
```
    git config --list
```

- 编辑Git配置文件
```
    git config -e [--global]
```

- 设置提交代码时的用户信息
```
    git config [--global] user.name "[name]"
    git config [--global] user.email "[email address]"
```