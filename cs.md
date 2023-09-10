# 本文为CS笔记
- [本文为CS笔记](#本文为cs笔记)
  - [插件](#插件)
  - [Powershell\&Windows terminal](#powershellwindows-terminal)
    - [各种快捷键](#各种快捷键)
    - [命令](#命令)
  - [git 版本管理系统](#git-版本管理系统)
    - [指令](#指令)
    - [与GitHub 的互动](#与github-的互动)
  - [Markdown](#markdown)
    - [基础语法](#基础语法)
  - [eg:](#eg)
    - [进阶语法](#进阶语法)

## 插件
1. caps2ctrl

---

## Powershell&Windows terminal
### 各种快捷键
**ctrl =**/**ctrl -** :界面的放大/缩小
**alt shift -**:竖直分栏
**alt shift =**:水平分栏
**ctrl shift f**:查找
**ctrl shift p**:打开命令菜单
**ctrl r**:历史记录查找
**ctrl l**:指针回到最上

---


### 命令
```
cd d:\freshman\All_notes //绝对路径
```

```
cd .\All_notes  //相对路径
```

```
pushd
popd
//存放和取出命令,可以多次使用
```

```
cd ~  //约定,回到用户目录
```

```
mkdir dir  //新建文件夹
```

```
ni item  //新建文件
```

```
rm dir  //删除(不可逆*慎用*)
```

```
ls
dir
//显示目录
```

```
cat c:\users\frank\.ssh\id_rsa.pub  
//显示文件内容
```

```
mv item item2 //移动或重命名
```

```
man ls  //查看手册*学习命令的好办法*
```
---

## git 版本管理系统

### 指令
1. 配置
```
git config --global user.name"Frank"
git config --global user.email"dongshen_rao@smail.nju.edu.cn"
//配置用户名和邮件地址

git config --list  //查看配置
```
2. 新建git仓库
```
git init
```

3. 添加文件到暂存区
```
git add filename
git add .  || git add -A  //添加所有文件
```

4. 提交暂存区的修改
```
git commit -m"message"
```
*tips:养成写好message的习惯,有时能节省很多时间*
==记得ctrl s 保存==

5. 查看git仓库
```
git status
```

6. 查看提交日志
```
git log
//键入:q 退出
```

7. 版本切换
```
git checkout version
```

8. 新建分支
```
git checkout -b<branch name>
```

9. 查看分支信息
```
git branch
```

10. 合并分支
```
git merge name_of_branch
```

---

### 与GitHub 的互动
1. SSH-key 的生成
```
cd ~/.ssh
ssh-keygen -t rsa -C"your email"
cat id_rsa.pub  //显示公钥
```

2. 关联SSH-key 与GitHub
**将公钥黏贴至GitHub的个人页面中**

3. 将本地库上传至GitHub
- GitHub网页选择[create a new repository]
- 将[push an existing repository from the command line]中的三条命令一次在git bash 中执行

4. 克隆仓库到本地
```
git clone 复制ssh
```

5. 拉取远程仓库数据并合并到当前分支
```
git pull  //= git fetch + git merge
```

6. 推送本地仓库的commit记录到远程仓库
```
git push
```
---


## Markdown
### 基础语法

1. 标题
```
# 这是一个一级标题
## 这是一个二级标题
...
###### 这是一个六级标题
```

2. 强调
```
**所强调的内容**
```
eg:**好好学习天天向上**

3. 斜体
```
*内容*
```
eg:*斜了*

4. 斜体并强调
```
***内容***
```

5. 高亮
```
==内容==
```
eg:==内容==

6. 代码块
```
```

7. 引用
```
> 引用的内容
```
eg:
> 书籍是人类进步的阶梯
> > 引用可嵌套

8. 无序列表
```
- 内容
```
eg:
- 内容

9. 有序列表
```
1. 内容
```

10. 上标
```
^上标^
```
eg:2^10^=1024

11. 下标
```
~下标~
```
eg:H~2~O

12. 注释
```
> 今日我们相聚于此, 是为了学习 Markdown 的使用, 它的教程对于全体「观众」而言, 值得足足两个硬币的支持鼓励![^1]

[^1]: 沃兹·基·硕德 改编自「公鸡」普契涅拉.
```

13. 链接
```
[链接内容](链接地址)
```
eg:[markdown教程](https://github.com/Sakiyary/Markdown-Typora-VSCode-Doc#user-content-fn-1-8f4a1227be7fc551eec52f739032ce39)

14. 任务列表
```
- [ ] 任务名
- [x] 任务名
```
eg:
- [ ] 完成markdown使用笔记
- [x] 摆烂

15. 表格
```
| 学号 | 姓名  | 年龄 |
| :--- | :---: | ---: | (引号的位置代表着 左对齐, 居中, 右对齐)
|114514|田所|24|
|1919810|浩三|25|
```
eg:

| 学号 | 姓名  | 年龄 |
| :--- | :---: | ---: |
|114514|田所|24|
|1919810|浩三|25|

16. 图片
直接拖入复制

17. 分割线
```
---
```
eg:
---
---
---

18. emoji表情
从[emoji大全](https://emojipedia.org/zh)中复制❤️

19. 删除线
```
~~~内容~~~
```
eg:~~~误~~~

---

### 进阶语法
1. 目录
若使用 VS Code 搭配 Markdown All in One 扩展, 可在 VS Code 的命令面板 (即 VS Code Command Palette) 输入 Create Table of Contents 自动生成目录, 且可在扩展设置中细调目录参数.

2. 内嵌HTML代码

用 "<> </>" 包围

- [ ] 学习HTML

