---
title: hexo搭建个人博的简陋记录
date: 2018-08-25 10:39:22
tags:
- tech
- hexo
---

## 安装git

如果是第一次使用，要先做如下操作：

<!--more-->

## 配置git

在命令行输入：  

`$ git config --global user.email "[you@example.com](mailto:you@example.com)"` 

`$ git config --global user.name "Your Name"`

利用 SSH 完成 Git 与 GitHub 的绑定：

[详细教程](https://blog.csdn.net/qq_35246620/article/details/69061355?locationNum=11&fps=1)

配置并绑定后方可通过git将本地内容推送到GitHub。

## 建gitpages

[官方教程](https://pages.github.com/)（非常简单粗暴）最终呈现会是一个大大的helloWorld。

[我的主页](https://0ltremar3.github.io/)

## 安装hexo

官方文档：( https://hexo.io/zh-cn/docs/ )

新手安装hexo的坑：`hexo init <folder>`->`hexo init x:\hexo` 不要加<>(有特殊意义)，会报错`bash: syntax error near unexpected token`

## 部署hexo到github
1. 与gitpages绑定：
    hexo文件夹下的_config.yml中设置deploy属性：
    ```
     deploy:
    type: git
    repo: git@github.com:0ltremar3/0ltremar3.github.io.git
    branch: master
    ```


2. 基本命令：

   ```
   hexo generate --生成个人博客所需的静态页面
   hexo server --本地预览
   hexo deploy --部署我们的个人博客
   hexo clean --清除缓存
   ```

3. 写文章

    ```
    hexo new "postName" --新建文章
    hexo new page "pageName" --新建页面
    ```

      生成的 .md文件在..:\\hexo\\source\\_posts里,我用Typora编辑。

4. 本地预览

   ```
   cd x://hexo
   hexo g
   hexo s
   ```


   浏览器打开[http://localhost:4000](http://localhost:4000/)即可预览。

5. 部署到github

   ```
   hexo clean
   hexo g -d
   ```

 
