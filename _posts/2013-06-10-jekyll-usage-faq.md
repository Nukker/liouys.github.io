---
layout: post
title: Jekyll使用问题总结
category: Jekyll
---

由于最近想使用Jekyll整理一个自己网站，但是使用Jekyll过程中遇到了几个问题，不过这些问题已经都解决了。为了方便后来者使用Jekyll少走弯路。

#问题一: 由于ruby版本安装不正确导致jekyll运行失败?

##问题现象

当按照[Running Jekyll on Windows][1]文章安装Jekyll的环境后，在其目录下运行jekyll.bat serve命令时出现以下错误：

	Configuration file: D:/Code/Jekyll/test/_config.yml
	 Source: D:/Code/Jekyll/test
	 Destination: D:/Code/Jekyll/test/_site
	 Generating... Liquid Exception: cannot load such file -- yajl/2.0/yajl in 2013-05-11-welcome-to-jekyll.markdown

##解决办法

请安装Ruby 1.9的版本可以解决此问题。

<hr>

#问题二: 当出现中文文章时，jekyll加载失败。

##问题现象

当在_posts目录下新建立一个文章时，其中标题采用中文比如： 

	文件名称：2013-06-10-jekyll-usage-faq.md
	---
	layout: post
	title: "Jekyll使用问题总结"
	category: Jekyll
	---
当运行jekyll.bat serve时会出现异常** Liquid error: invalid byte sequence in GB2312**。

##解决办法

修改ruby安装目录下\lib\ruby\gems\1.9.1\gems\jekyll-1.0.2\lib\jekyll\convertible.rb:31行  

修改之前：  

{% highlight ruby %}
	self.content = File.read(File.join(base, name))  
{% endhighlight %}

修改之后：  

{% highlight ruby %}
	self.content = File.read(File.join(base, name), :encoding => "utf-8")
{% endhighlight %}


[1]: http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html
