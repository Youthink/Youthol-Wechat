# Youthol-Wechat
青春在线 微信智慧校园

## 图书馆
>图书到期自动发送提醒邮件 

### 技术栈
后端：PHP CodeIgniter + MySQL

前端：WeUI + less

Linux CronTab 定时任务 

### 部署
1、导入数据库

2、修改applications/config/config.php
```
$config['base_url'] = 'http://localhost/Youthol-Wechat'; //在这里替换域名
```
3、修改applications/config/database.php
```
$db['default'] = array(
	'dsn'	=> '',
	'hostname' => 'localhost',
	'username' => 'root', //修改你的用户名
	'password' => '', //修改你的密码
	'database' => 'youthol_wechat'
);
```
4、CronTab 定时任务
>Linux服务器环境(虚拟主机、windows自行百度)

```
crontab -e     //新建定时任务
``` 
输入
```
0 18 0 0 0 lynx http://localhost/Youthol-Wechat/index.php/lib/scheduledEmail --dump           //记得换成你的域名
```
```
crontab -l     //查看定时任务
``` 






