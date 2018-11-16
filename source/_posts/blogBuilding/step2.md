---
title:  配置hexo + github
date: 2018-11-09
categories: 
- 博客搭建
tags:
- 博客搭建
- 配置hexo + github
---
* 创建github账户，创建代码库
* 创建秘钥，将本地仓库与远程仓库建立连接
  1. `ssh-keygen -t rsa -C "xxxx@qq.com"` 命令行中输入该指令，创建秘钥
  2. 打开 `C:\Users\lijun.ssh\id_rsa.pub` 中的文件，将里面内容复制黏贴进 `https://github.com/settings/ssh` 的new SSH key中
  3. 输入 `ssh -T git@github.com` 测试是否成功，若返回 `Hi lijun! You've successfully authenticated, but GitHub does not provide shell access.` 即成功!
  4. 配置git个人信息
  ```
  git config --global user.name "xxxxx"
  git config --global user.email "xxxxx@qq.com"
  ```
  5. 配置 Deployment
  在`_config.yml`中找到`Deployment`,配置以下信息
  ```
  # Deployment
  ## Docs: https://hexo.io/docs/deployment.html
  deploy:
    type: git
    repo: git@github.com:lijun/lijun.github.io.git
    branch: master
  ```
  6. 本地提交到github
  ```havascript
  // 删除旧的public文件
  hexo clean
  // 生成新的public文件
  hexo g
  // 启动服务
  hexo s
  // 开始部署到github
  hexo d
  ```