

# GitHub

## 关键字查询

awesome,去此标签类别中查询项目

tutorial,查询资料，书籍，文档

sample,查询对应技术的代码样本

## 三要素

### repository 仓库

仓库是GitHub项目管理存储基本单位

一个仓库中存储一个项目，一个用户可以拥有多个仓库，一般仓库分为public和private

### commit 提交

程序员在整个开发周期，有大量的对代码资源的送代和修改，都可以通过commit的方式进行记
录，便于程序员回溯代码，即是这些代码被删除

便于梳理开发流程，提交便于使用者观察整个工程的开发途程以及设计流程

### branch 分支

在仓库中可以包含多个分支，分支才是代码文件的第一存储单位，默认的仓库分支为master/main

不仅可以管理代码存储， 便于多人协作开发

![image-20240611112551624](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611112551624.png)

## 仓库内容

### code			 

资源存储，代码资源，二进制， 项目管理脚本，许可证等等

### issues

使用时遇到的bug或进行提交， 等待反馈

### README 

使用markdown语言编写，工程自述文件，开发进度，版本更新，使用介绍等等

### LICENSE许可证

GPL 2.0,3.0	Apahce 2.0	Mit，这些许可证，给使用者最大使用权限以及最少的限制

### Git软件

分布式版本控制系统，仓库管理软件，使用git管理私人代码或企业代码

![image-20240611121636027](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611121636027.png)

### Git命令

#### ssh远程访问

ssh-keygen -t rsa -C "邮箱"	//创建本地密文

去对应的自录查找密文文件

![image-20240611141336669](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611141336669.png)

复制.pub内容，粘贴到新建的ssh keys

![image-20240611141438192](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611141438192.png)

ssh -T git@github.com	//测试关联是否成功

![image-20240611143759883](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611143759883.png)

#### 1.如何让网站的账户与设备绑定，后续完成代码的管理，上传下载

git init	//创建本地仓库	后续对仓库的操作，都要在仓库位置（master）

git config --list	//查看git的配置文件

git config --global user.email "邮箱"	//配置 Git 的全局用户电子邮件地址

git config --global user.name "用户名"	//配置 Git 的全局用户名

#### 2.为目标仓库起别名，定位目标仓库，后续上传

git remote add origin "ssh地址"	//为ssh仓库地址创建别名origin

git remote remove origin	//删除origin别名

#### 3.本地设备与云端仓库的交互逻辑

![image-20240611152013829](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611152013829.png)

touch code.c

vi code.c

git add code.c

git commit -m "说明"

git push origin master

github刷新

#### 4.删除

##### 删除代码

git status	//查看本地仓库状态

git restore code.c	//恢复被删除文件（仓库存在）

git rm code.c	//删除本地文件并除仓库数据

![image-20240611155918904](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611155918904.png)

删除可以提交

git commit -m "说明"

git push origin master

##### 删除仓库

仓库界面->设置

![image-20240611201442852](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611201442852.png)

##### 删除账号

个人中心->account

![image-20240611201816605](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611201816605.png)

#### 5.依赖关系被破坏（云端比本地代码新）

本地内容要比云端新，完成更新替换，但是如果直接修改云端内容，导致，本地内容无法再次提交

##### 解决方法（三选一）

*先拉取git pull云端内容与本地内容合并或操作，而后再次推即可

git pull --rebase origin master

![image-20240611161944334](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611161944334.png)

###### 方法1

git rebase --abort

###### 方法2

git rebase --skip

忽略本地内容保留云端内容

###### 方法3

git rebase --continue

#### 6.下载开源代码

复制https地址

![image-20240611164311100](C:\Users\liuyu\AppData\Roaming\Typora\typora-user-images\image-20240611164311100.png)



git clone "https仓库地址”	//下载开源项目code资源

#### 分支branch

*关于分支的相关命令，创建分支、选择分支、合并分支等等

#### markdown语言

.md文件

终端显示行号		:set nu

Markdown，文本修饰语言，用特殊符号修饰正文效果

# 标题修饰符\#

# （一级标题）

## （二级标题）

### (三级标题)

## 正文内容

输入正文内容，但是如果需要换行，用\<br\>标签

## 修饰正文

*一段测试文本*
**一段测试文本**
***一段测试文本***
~~一段测试文本~~

## 分割线

用\-\-\- 表示分割线

---

## 引用\>表示

> 一级引用
>
> > 二级引用
> >
> > > 三级引用
> > >
> > > > 四级引用

## 列表修饰符

### 无序列表 \*

* 123
  * 1
  * 2
  * 3
* 456
  * 4
  * 5
  * 6

## 有序列表 1.

1. 编程语言
   1. C
   2. C++
   3. Python
2. 计算机
   1. 计算机网络
   2. 操作系统
   3. 计算机组成原理
   4. 数据结构与算法

### 表格

| 字母                                                         | 数字 | 排行 |
| :----------------------------------------------------------- | :--: | ---: |
| --\|:--:\|--:表示这个表格第一列靠左对齐，第二列居中，第三列靠右 |      |      |
| A                                                            | 123  |    1 |
| B                                                            | 456  |    2 |
| C                                                            | 789  |    3 |

### 代码片段

```C
#include<stdio.h>
int main(){
printf("hello\n");
return 0;
}
```

这是一个测试文本，将`关键字`重点显示

### 超链接技术

[Github](https://www.github.com "点击访问")

### 插入图片

![桌面壁纸](C://Users//liuyu//Downloads//桌面壁纸.png "悬停标题")



