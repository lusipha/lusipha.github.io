---
layout: post_item
title:  '用Github Pages搭建免费个人博客'
date:   2014-02-27
author: 薛笛
categories : [写作技巧]
tags:	[建站]
---


经过几天的折腾，终于搞掂了一个托管到Github Pages上的Blog。总体难度不大，时间主要耗在找教程、查找模板、更改配置、熟悉语法等一些琐碎的事情上。开始的时候折腾了几个模板都感觉不满意，最后还是Fork了jekyll主页的project改了改才算完工。整体框架搭好了之后，一般就不用再折腾了，单纯码字过程还是相当简单和流畅的。

<!--more-->

### 关于使用Github Pages搭建个人Blog的一些经验

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

【主题】如果对默认版式不满意，有些[demo][theme_demo]可供参考

###	Markdown功能和用法
【基础语法】Markdown语法中文版文档在[这里][md_grammar_cn]，原始版英文文档在[这里][md_grammar_en]

【外链图片】博客文章一般都有配图的需要，不过由于github限定了一个免费仓库最多300M空间，所以还是省着点用，把更多的空间留给文字吧。通常的方法是寻找一个可以外链图片的空间或图床，如果肯花钱买空间自然不用愁；但若不想花钱，又想有稳定、快速、没水印的图床就没那么容易了。

我喜欢用微博相册做外链图床，简单又方便。貌似新浪和腾讯的微博把图片发上去就能得到下载url，还是挺方便的，只是右下角都有水印，不过看在没给钱的份上就忍了。为了预防万一，最好还是把图片在本地仓库的文件夹里，并且在.gitignore里面把这个目录加进去，这样即省了流量、也可以保证图床失效了之后图片还有救，到时候只是费点事改下链接就行了。最后发个外链的俊男美女测试图：

![微博相册图床](http://t2.qpic.cn/mblogpic/5b24796b20e92a2c0844/2000 "测试图片")

【Block Quotes】
> 文本块演示
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
【有特点的标签--与公式冲突？？】

<div class="note">
  <h5>ProTips™ help you get more from Jekyll</h5>
  <p>These are tips and tricks that will help you be a Jekyll wizard!</p>
</div>

<div class="note info">
  <h5>Notes are handy pieces of information</h5>
  <p>These are for the extra tidbits sometimes necessary to understand
     Jekyll.</p>
</div>

<div class="note warning">
  <h5>Warnings help you not blow things up</h5>
  <p>Be aware of these messages if you wish to avoid certain death.</p>
</div>

<div class="note unreleased">
  <h5>You'll see this by a feature that hasn't been released</h5>
  <p>Some pieces of this website are for future versions of Jekyll that
    are not yet released.</p>
</div>


【数学公式】  
{% include mathjax.html %}
有人总结了写数学公式的[一些方法][math]，这里我还是选择了[Mathjax][]。使用Mathjax有两种方式：	

*	通过Mathjax的CDN来下载和渲染公式 
*	把js文件安装到网站里，就可以用本地路径渲染了  

个人博客选第一种也行，反正是托管到svr上的。行内公式是这样：\\(E=mc^2\\)，行间公式是这样：$$x_{1,2} = \frac{-b \pm \sqrt{b^2-4ac}}{2b}.$$

最后再来个牛叉的欧拉公式：\\(\mathrm{e}^{- \mathrm{i} \pi} + 1 = 0\\)

【表格】

未完待续......


[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll_doc]:    http://jekyllrb.com
[md_grammar_cn]: http://wowubuntu.com/markdown/
[md_grammar_en]: http://daringfireball.net
[theme_demo]: http://yuanyong.org/blog/collect-jekyll-theme.html
[math]: http://scorpiohw.github.io/blog/2013/01/29/wei-markdowntian-jia-shu-xue-gong-shi/
[Mathjax]: http://www.mathjax.org/
