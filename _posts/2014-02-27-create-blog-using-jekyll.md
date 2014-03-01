---
layout: post
title:  "Github+Jekyll+Markdown搭建免费的个人博客"
date:   2014-02-27
tags:	写作技巧
categories: 写作技巧
---


### 关于使用Github Pages搭建个人Blog的相关教程


经过几天的折腾，总结了一下从无到有建立一个托管到Github Pages上的Blog，大致有如下几个关键过程：

* 在Github上注册一个帐号，创建一个`username.github.io`的仓库
* 在Github上寻找合适的或你喜欢的blog仓库，fork到自己的空间中，并pull到本地
* 安装`jekyll`及其相关组件，调用`jekyll new`创建一个blog的架子
* 花点时间到[Jekyll docs][jekyll]看一下jekyll的使用和配置
* 用fork回来的内容替（包括_config.yml配置）换jekyll生成的框架，本地调试，直到满意为止
* 提交到Github上，这时候就可以在`http://username.github.io`看到页面了
* Dirty work完成！学习一下Markdown语法，剩下的就主要是写作了


### 关于Jekyll的使用

【_config.yml配置】有文件更新就自动更新站点，本地调试的时候很有用`auto:	true`

【jekyll本地调试】`jekyll serve --baseurl '' --watch`，其中`--watch`是为了能看到运行的详细信息


###	Markdown功能和用法
【基础语法】Markdown语法中文版文档在[这里][md_grammar_cn]，原始版英文文档在[这里][md_grammar_en]

【外链图片】博客文章一般都有配图的需要，不过由于github限定了一个免费仓库最多300M空间，所以还是省着点用，把更多的空间留给文字吧。通常的方法是寻找一个可以外链图片的空间或图床，如果肯花钱买空间自然不用愁；但若不想花钱，又想有稳定、快速、没水印的图床就没那么容易了。

当然，萝卜白菜各有所爱，我还是喜欢用微博相册做外链图床，简单又方便。貌似新浪和腾讯的微博把图片发上去就能得到下载url，还是挺方便的，我一直用它。但是为了预防万一，最好还是把图片在本地仓库的文件夹里，并且在.gitignore里面把这个目录加进去，这样万一图床失效了图片还有救。只是费点事改下链接就行了。最后发个养眼的俊男美女来作为外链图片的小结吧：

![微博相册图床](http://t2.qpic.cn/mblogpic/5b24796b20e92a2c0844/2000 "测试图片")

【Block Quotes】
>文本块演示
> >嵌套文本块演示

【代码格式】
{% highlight C++ %}
#include <stdio>
int main(int argc, char ** argv)
{
	printf("hello world!");
	return 0;
}
#=> prints 'hello world!' to STDOUT.
{% endhighlight %}

```sh
sudo vi /etc/network/interfaces
```

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll_doc]:    http://jekyllrb.com
[md_grammar_cn]: http://markdown.cn
[md_grammar_en]: http://daringfireball.net