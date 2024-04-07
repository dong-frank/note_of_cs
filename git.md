# git 版本管理系统
- [git 版本管理系统](#git-版本管理系统)
  - [指令](#指令)
  - [与GitHub 的互动](#与github-的互动)

## 指令
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

## 与GitHub 的互动
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
```
git remote add origin git@github.com:dong-frank/1.git
git branch -M main
git push -u origin main
```
```
git pull origin master –-allow-unrelated-histories
```

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
-