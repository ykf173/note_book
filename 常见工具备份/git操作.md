## git骚操作

* 1. 将不是git文件的目录,添加到新的git分支
```bash
git init
git add . 将当前目录
git branch 新分支名称
git push 待提交目录
提交到指定分支 
git push --set-upstream git线上地址 分支名
```

* 2. 删除缓冲区不想提交的数据
```bash
git rm -r --cached 文件 ./\*.pyc
```

* 3. 连接远程
```bash
git init 
git remote add origin ssh:/git@code.ii-ai.tech:2222/nlp/contract_review_train.git
git remote set-url origin
git remote update origin --prune
```

* 4. 切分支之前，删除本地无用数据
```bash
git clean -d -fx
表示：删除一些没有 git add的文件
git clean 参数
	-n 显示将要删除的文件和目录
	-x -----删除忽略文件已经对git来说不识别的文件
	-d -----删除未被添加到git的路径中的文件
	-f -----强制运行

git clean -n
git clean -df
git clean -f
```

* 5. 重置修改
```bash
git reset. —-hard
```

* 6. 多人开发
```bash
git stash
git commit 
git stash list
git stash pop
```

* git 日志查看

```bash 
git status
git log --graph --oneline
```

* 问题1：permission denied

  ![image-20230302143432374](/Users/langming/我的/private/笔记/常见工具备份/assets/image-20230302143432374.png)

* 解决方案：

> 1. 可能是被墙了
> 2. 采用ssh方式`git remote add origin git@github.com:ykf173/note_book.git`

* 问题2:：报错：git 错误 fatal: Not a valid object name: 'master'. 
  	本地需要commit，建立连接，但是这会直接交到master ????
* 同时使用GitHub，Gitlab



* github设置本地代理

  ```bash
  # Host github.com
  #    ProxyCommand nc -X 5 -x 127.0.0.1:1080 %h %p
  ```

  