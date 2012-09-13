title: Host static website on Heroku
author: Makzan
date: 2012-09-12 22:00
template: article.jade

Heroku is convenient for me to get something up and running in short time. All from my terminal and git repo. It doesn't have issue for project with PHP, RoR or Node.js. But what I need now is a plain HTML website. 

## Two Approaches 

I just found two approaches to host static websites on [Heroku][1].


### 1. Fake it as PHP

This approach is from [Kenneth Reitz][2]. It creates a PHP file to make Heroku thinks this project is a PHP project.


> ### Elegant Static Sites on Cedar
> 
> First, lets turn your site into a PHP "application":
> 
> `$ touch index.php`
>
> 　
> 
> Next, we can fully disable Apache's PHP engine:
> 
> `$ echo 'php_flag engine off' > .htaccess`
>
> 　
> 
> When you push this up, you'll have a bare Apache instance serving up the contents of your site to the world. Best yet, you can do all of the stupid .htaccess tricks that you could on on any traditional shared hosting platform.

### 2. Heroku Buildpack

I found another [easier approach][4] from [Jack Pearkes][3] on Github. It uses the custom buildpack approach that makes this works right after creating the app.

> `heroku create --stack cedar --buildpack https://github.com/pearkes/heroku-buildpack-static`

Currently, the current website is hosted on Heorku by using the buildpack approach.

　

▋Makzan • 娜菲 • 晴

[1]: http://heroku.com
[2]: http://kennethreitz.com/static-sites-on-heroku-cedar.html
[3]: https://github.com/pearkes
[4]: https://github.com/pearkes/heroku-buildpack-static