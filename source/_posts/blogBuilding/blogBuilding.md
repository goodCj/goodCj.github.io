---
title: 安装必需组件
date: 2018-11-08 13:57:00
categories: 
- 博客搭建
tags:
- 博客搭建
- hexo、git命令
---
# 安装必备组件

1. 安装**node.js**
[node官网](https://nodejs.org/en/ "node官网")

2. 安装**git**工具
[git官网](https://git-scm.com/ "git官网")

3. 安装**hexo**
    * 先创建一个文件夹，在该文件夹中git bush

    * 安装hexo命令 `npm i -g hexo`

    * 初始化命令 `hexo init`
```
public：存放的是生成的页面
scaffolds：命令生成文章等的模板
source：用命令创建的各种文章
themes：主题
_config.yml：整个博客的配置
```
<!-- more -->

# 博客搭建步骤

1. 创建github账户，创建代码库 

2. 创建秘钥，将本地仓库与远程仓库建立连接

    * `ssh-keygen -t rsa -C "xxxx@qq.com"` 命令行中输入该指令，创建秘钥

    * 打开 `C:\Users\lijun.ssh\id_rsa.pub` 中的文件，将里面内容复制黏贴进 `https://github.com/settings/ssh` 的new SSH key中
    * 输入 `ssh -T git@github.com` 测试是否成功，若返回 `Hi lijun! You've successfully authenticated, but GitHub does not provide shell access.` 即成功!

3. 配置git个人信息
  ```
  git config --global user.name "xxxxx"
  git config --global user.email "xxxxx@qq.com"
  ```

4. 配置 Deployment
  在hexo配置文件夹中站点配置文件`_config.yml`中找到`Deployment`,配置以下信息
  ```
  # Deployment
  ## Docs: https://hexo.io/docs/deployment.html
  deploy:
    type: git
    repo: git@github.com:lijun/lijun.github.io.git
    branch: master
  ```
5. hexo命令本地提交到github
  ```havascript
  // 删除旧的public文件
  hexo clean
  // 生成新的public文件
  hexo g
  // 启动服务
  hexo s
  // 开始部署到github
  hexo d
  //创建新md
  hexo new page 文件名
  ```


# 将hexo迁移到另一台电脑

1. 在`goodcj.github.io`仓库中新创建一个分支，分支名为`hexo`

2. 将旧电脑的hexo的部署环境文件夹中的所有东西上传到新分支`hexo`中

    * 将 goodcj.github.io 仓库 git clone 克隆到本地新建文件夹中
    * 此时可以查看本地分支为master，使用命令新建一个分支并切换到该分支中，并删除该分支中除了.git的所有文件
    * 将旧电脑的hexo部署环境中所有文件黏贴到该分支中
    * 使用git命令将该分支中上传到远程仓库中


# 创建新分支，上传代码的git命令

* git branch                  查看分支
* git branch   新分支名字      创建新分支
* git checkout 新分支名字      切换到新分支
* git status                  查看分支状态
* git add .                   将所有文件添加进缓存中
* git commit -m "注释"        将暂存区中的文件添加到本地仓库
* git push origin 新分支名字   将文件上传到远程仓库的对应分支中
* git clone    分支地址        克隆远程仓库对应分支文件
* git pull                    拉取远程仓库对应分支文件


