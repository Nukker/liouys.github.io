---
published: false
---

# Fedora下一代Yum软件包管理器DNF

## DNF简介

从Fedora 18 Beta的软件仓库中就可以安装DNF（安装命令: sudo yum install dnf），其使用libsolv提升依赖关系处理速度。

DNF是一个新的软件包管理库，是建立在libsolv和其后端之上构建。 DNF相比yum易于维护，并拥有更好的性能，同时也使用更小的内存占用。 在Fedora 18中的新的包管理器dnf和yum可以并存。DNF可以使用在所有基于RPM Linux发行版本上。

## 使用命令

dnf命令格式：  
> dnf [options] COMMAND

主要命令选项包括：  
> **check-update**   检查是否有软件包更新  
     **clean**删除缓存的数据  
     **distribution-synchronization**已同步软件包到最新可用版本  
     **downgrade**降级包  
     **erase**从系统中移除一个或多个软件包  
     **help**显示用法信息  
     **history**显示或使用事务历史  
     **info**显示关于软件包或组的详细信息  
     **install**向系统中安装一个或多个软件包  
     **list**列出一个或一组软件包  
     **makecache**创建元数据缓存  
     **provides**查找提供指定内容的软件包  
     **reinstall**覆盖安装一个包  
     **repolist**显示已配置的仓库  
     **search**在软件包详细信息中搜索指定字符串  
     **upgrade**更新系统中的一个或多个软件包

dnf命令使用例子：  
> 安装一个软件包nmap  
     # dnf install nmap

命令格式与yum几乎一样。详细命令手册：[请进=>](http://akozumpl.github.io/dnf/command_ref.html)

## 注：

libsolv： openSuSE开发，并托管在https://github.com/openSUSE/libsolv。

