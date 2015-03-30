---
layout: post
title: MacOS上利用Sublime与Ctags查看代码
date: 2015-03-30 10:44AM
categories: Mac
tags: Mac
excerpt: MacOS上代码查看工具。
---

<p>下载安装SublimteText,搜索安装了个破解版，还不错。</p>

<p>利用brew安装Ctags</p>
    brew install ctags
<p>因为原来系统下有ctags，在/usr/bin/ctags;</p>
<p>利用brew安装完之后，会安装在/usr/local/Cellar/ctags/5.8_1</p>

<p>创建别名:</p>
    alias ctags="`brew --prefix`/bin/ctags"
<p>并且将别名添加到系统脚本<p>
    alias ctags >> ~/.bash_profile
<p>然后就可以利用Sublime和Ctags查看代码</p>
利用`ctags -R -f .tags`,代码之间可以互相切换
