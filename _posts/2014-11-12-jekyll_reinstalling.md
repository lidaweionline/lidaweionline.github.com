---
layout: post
title: jekyll重新安装
categories:
- ubuntu 
tags:
- jekyll rvm ruby
-----------------------
---------------------

jekyll安装时报错failed to build a native extension.
解决办法：
1.安装rvm
2.更新ruby
3.重装jekyll
步骤：
查看curl安装情况dpkg -s curl
安装rvm  curl -L get.rvm.io | bash -s stable
执行rvm  $HOME/.rvm/scripts/rvm
查看rvm版本  rvm -v
查看ruby版本  rvm list
查看可以安装ruby版本 rvm list known
选择版本安装  rvm install x.x.x-head
设置默认使用版本 rvm use ruby-x.x.x-head --default 
查看ruby版本  ruby -v
jekyll serve时报错，md文件需要rdiscount依赖包。
安装rdiscount依赖包时报错failed to build native gem package。
gem install rdiscount搞定。


