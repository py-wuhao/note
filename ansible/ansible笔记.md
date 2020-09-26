# ansible

## ansible安装

略

## 建立ssh信任关系

1. 主机生成密钥

   ssh-keygen -t rsa

2. 拷贝公钥到被控制机

   ssh-copy-id root@192.168.1.6

## 添加资产

略

## 常用命令

ad-Hoc

```shell
ansible pattern -m module -a argument
```



1. 查看所有资产

   ```shell
   ansible all  --list-host
   ```

2. 查看模块文档

   ```shell
   ansible-doc modeule
   ```

3. shell

   ```shell
   ansible all -m shell -a "ls"
   ```

4. script 拷贝本地脚本到被管理节点执行

   ```shell
   ansible all -m script -a "/root/home/a.sh"
   ```

5. copy 拷贝本地文件到被管理节点

   ```shell
   ansible all -m copy -a 'src=/root/ansible/a.sh dest=/root/a.sh'
   ```

6. yum 安装卸载软件

   ```shell
   ansible all -m yum -a 'name=httpd state=present'
   ansible all -m yum -a 'name=httpd state=removed'
   ```

7. systemd 管理服务

   ```shell
   ansible all -m systemd -a 'daemon_reload=yes'
   ansible all -m systemd -a 'name=httpd state=started'
   ansible all -m systemd -a 'name=httpd state=stoped'
   ```

8. file 对被控节点文件操作

   ```shell
   略
   ```

9. cron 计划任务

   ```shell
   略
   ```

10. debug 传参调试

    ```shell
    略
    ```

11. template  和copy一样 多了变量替换

    ```shell
    略
    ```


## 变量

1. 全局变量
2. 剧本变量
3. 资产变量
4. facts变量

## 任务控制

### 条件判断	when

### 循环 	with_items  	or    loop

### 选择执行 	tags

### 触发器 	notify	handlers



## jinja2模板

略

## roles

### 结构

```shell
role/
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── meta
│   └── main.yml
├── tasks
│   └── main.yml
├── templates
└── vars
    └── main.yml
```





