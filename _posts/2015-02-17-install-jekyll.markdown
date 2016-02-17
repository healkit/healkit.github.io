---
layout: post
title:  "Install Jekyll!"
date:   2016-02-17 16:27:25 +0000
categories: jekyll install
---

安装环境`Ubuntu`
1. 安装ruby
  {% highlight ruby %}
  sudo apt-get install ruby2.0*
  {% endhighlight %}
不单要安装ruby2.0，还需要ruby的开发环境
2. 更改默认ruby
  {% highlight ruby %}
  sudo cp /usr/bin/ruby /usr/bin/ruby.bat
  sudo cp /usr/bin/gem /usr/bin/gem.bat
  sudo cp /usr/bin/ruby2.0 /usr/bin/ruby
  sudo cp /usr/bin/gem2.0 /usr/bin/gem
  {% endhighlight %}
3. 安装jekyll
  {% highlight ruby %}
  sudo gem install github-pages
  {% endhighlight %}
  
问题:
1. ruby2.0 没有安装完全
{% highlight ruby %}
$ sudo gem install github-pages
Building native extensions.  This could take a while...
ERROR:  Error installing github-pages:
	ERROR: Failed to build gem native extension.

    /usr/bin/ruby2.0 extconf.rb
mkmf.rb can't find header files for ruby at /usr/lib/ruby/include/ruby.h


Gem files will remain installed in /var/lib/gems/2.0.0/gems/ffi-1.9.10 for inspection.
Results logged to /var/lib/gems/2.0.0/gems/ffi-1.9.10/ext/ffi_c/gem_make.out
{% endhighlight %}
解决方法就是`sudo apt-get install ruby2.0*`的`*`
2. Build Warning: Layout 'post' requested in welcome-to-jekyll.markdown does not exist.
{% highlight ruby %}
$ jekyll serve
Configuration file: none
            Source: /home/ubuntu/Blog/healkit/_posts
       Destination: /home/ubuntu/Blog/healkit/_posts/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
     Build Warning: Layout 'post' requested in 2016-02-17-welcome-to-jekyll.markdown does not exist.
                    done in 0.155 seconds.
 Auto-regeneration: enabled for '/home/ubuntu/Blog/healkit/_posts'
Configuration file: none
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
  {% endhighlight %}
  解决方法在_config.yml 加入`exclude: [vendor]`


