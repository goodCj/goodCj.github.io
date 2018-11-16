---
title:  将hexo迁移到另一台电脑
date: 2018-11-16
categories: 
- 博客搭建
tags:
- 博客搭建
- 将hexo迁移到另一台电脑
- git命令
---
* 在`goodcj.github.io`仓库中新创建一个分支，分支名为`hexo`

* 将旧电脑的hexo的部署环境文件夹中的所有东西上传到新分支`hexo`中

    ```javascript
    1、将 goodcj.github.io 仓库 git clone 克隆到本地新建文件夹中
    2、此时可以查看本地分支为master，使用命令新建一个分支并切换到该分支中，并删除该分支中除了.git的所有文件
    3、将旧电脑的hexo部署环境中所有文件黏贴到该分支中
    4、使用git命令将该分支中上传到远程仓库中
    ```

* 创建新分支，上传代码的git命令

    ```javascript
    1、git branch                  查看分支
    2、git branch   新分支名字      创建新分支
    3、git checkout 新分支名字      切换到新分支
    4、git status                  查看分支状态
    5、git add .                   将所有文件添加进缓存中
    6、git commit -m "注释"        将暂存区中的文件添加到本地仓库
    7、git push origin 新分支名字   将文件上传到远程仓库的对应分支中
    ```
