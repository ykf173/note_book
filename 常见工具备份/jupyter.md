### 初始化工作

* 安装

```bash
pip install -U jupyter
```

* 启动

```bash
jupyter notebook --no-browser --port 16800
```

* 配置远程启动（远程访问服务器）[知乎](https://zhuanlan.zhihu.com/p/64524822)
​	  1. 生成配置文件

​			`jupyter notebook --generate-config`
![image-20230301145211026](/Users/langming/我的/private/笔记/常见工具备份/assets/image-20230301145211026.png)

​		2. 设置访问密码			

​			`jupyter notebook passwd`

![image-20230301144837787](/Users/langming/我的/private/笔记/常见工具备份/assets/image-20230301144837787.png)

​		3. 免登录访问

```python3
In [1]: from notebook.auth import passwd
In [2]: passwd()
Enter password:
Verify password:
Out[2]: '*********'
```

（1）修改配置文件 vim ~/.jupyter/jupyter_notebook_config.py

![image-20230301145929446](/Users/langming/我的/private/笔记/常见工具备份/assets/image-20230301145929446.png)

```python3
c.NotebookApp.password = u'sha1:67c9e60bb8b6:9ffede0    #设置免密登陆
c.NotebookApp.allow_remote_access = True
c.NotebookApp.ip='*'
c.NotebookApp.open_browser = False
```

​		4. 开放防火墙端口

> `sudo firewall-cmd --zone=public --add-port=端口号/tcp --permanen`
>
> 如遇：`env: ‘firewall-cmd’: No such file or directory`问题
>
> 安装：sudo apt install firewall
>
> 重启防火墙：`sudo systemctl restart firewalld`

* 设置启动目录`vim ~/.jupyter/jupyter_notebook_config.py`

```bash
 c.NotebookApp.notebook_dir = '工作目录'
```


