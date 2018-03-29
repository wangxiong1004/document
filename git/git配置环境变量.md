## git配置环境变量

-- 参考资料

    [http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000](http://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000)

-- 设置
```
    如果出现git不是内部或外部命令，就需要找到git的安装目录，复制git里面的bin目录路径：C:\Program Files\Git\bin	

    打开环境变量，找到Administrator的变量里面的PATH  
    ----> 再把你刚刚复制的路径粘贴进去
    ----> 点击确定
    ----> 关掉CMD控制台，再重新打开，这个时候就可以运行git了
```

- 命令添加
```
    set PATH=%PATH%;C:\Program Files\Git\bin
```