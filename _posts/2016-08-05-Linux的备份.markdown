---
layout: post
title:  "Linux的备份"
date:   2016-08-05 11:17:32 +0800
categories: jekyll update
--- 

## Linux的备份 ##

Rsync备份linux  Shell脚本

	#!/bin/bash
	# 将备份列表文件的路径保存到变量中
	backupf='/tmp/bckup.txt'
	# 输入一个提示信息
	echo "Shell Script Backup Your Files / Directories Using rsync"
	# 检查是否输入了目标服务器，如果为空就再次提示用户输入
	while [ x$desthost = "x" ]; do
	# 提示用户输入目标服务器地址并保存到变量
	read -p "Destination backup Server : " desthost
	# 结束循环
	done
	# 检查是否输入了目标文件夹，如果为空就再次提示用户输入
	while [ x$destpath = "x" ]; do
	# 提示用户输入目标文件夹并保存到变量
	read -p "Destination Folder : " destpath
	# 结束循环
	done
	# 检查是否输入了目标服务器密码，如果为空就再次提示用户输入
	while [ x$password = "x" ]; do
	# 提示用户输入密码并保存到变量
	# 使用 -s 选项不回显输入的密码
	read -sp "Password : " password
	# 结束循环
	done
	# 逐行读取备份列表文件
	for line in `cat $backupf`
	# 对每一行都进行处理
	do
	# 显示要被复制的文件/文件夹名称
	echo "Copying $line ... "
	# 使用 expect 来在脚本中输入密码
	/usr/bin/expect << EOD
	# 推荐设置超时为 -1 
	set timeout -1
	# 通过 rsync 复制文件/文件夹到目标位置，使用 expect 的组成部分 spawn 命令
	spawn rsync -ar ${line} ${desthost}:${destpath}
	# 上一行命令会等待 “password” 提示
	expect "*?assword:*"
	# 在脚本中提供密码
	send "${password}\r"
	# 等待文件结束符（远程服务器处理完了所有事情）
	expect eof
	# 结束 expect 脚本
	EOD
	# 显示结束
	echo "DONE"
	# 完成
	done


Rsync
参考

* [Shell脚本：使用rsync备份文件/目录](https://linux.cn/article-5694-1.html)
* [Linux 下的十一款一流备份实用工具](https://linux.cn/article-7183-1.html)
* [如何用 Rsync 来备份 Linux 文件](http://wowubuntu.com/rsync.html)
* [使用rsync备份完整Linux操作系统](https://huataihuang.gitbooks.io/cloud-atlas/content/os/linux/backup/full_system_backup_with_rsync.html)
* [如何在Linux下使用rsync](https://linux.cn/article-4503-1.html)
* [用rsync备份一台linux服务器上的数据/](http://www.zphj1987.com/2015/03/22/用rsync备份一台linux服务器上的数据/)
* [Linux命令之文件同步、定时备份 -rsync,cron,crontab](http://blog.csdn.net/wangjunjun2008/article/details/38658539)
