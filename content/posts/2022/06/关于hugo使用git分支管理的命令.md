---
title: "关于hugo使用git分支管理的命令"
date: 2022-06-18T21:53:38+08:00
draft: false
categories:
- Git
- Hugo
tags:
- Hugo
- Git
---

## 简单的几个命令	 

​	就是一个仓库创建两个分支 然后 都提交到远程仓库；然后每次合并文件到public的分支 ；存放public文件的仓库作为默认展示分支； 



```shell
# 创建分支
git checkout -b public

# 切换分支j
git checkout public 

# 复制文件到另外一个分支
git checkout main -- public


#然后 git push 
## 添加远程仓库
git remote add origin git@github.com:niantoudeyisi/niantoudeyisi.github.io.git

## 第一次需要明确远程分支 后面只需要git push即可
git push -u origin public


# 还有将本地一个仓库 推送到另一个远程仓库的另一个分支上
# 就是将 url是仓库地址 ；就是将本地master分支推送到远程deploy分支
git push -f url master:deploy  

# 后续基本上就是
git add . && git commit -m  "20221007" && git push 
```

```
然后我这边 就是本地blog文件 resource推送到一个分支 
然后进入public目录将内容推送到另一个用于展示github pages的分支
```
