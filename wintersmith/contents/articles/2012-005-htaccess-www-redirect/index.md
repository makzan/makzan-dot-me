title: Redirect between www and naked domain
author: Makzan
date: 2012-09-14 14:00
template: article.jade


A quick note to use .htaccess to redirect between www and naked domain.


I found this rule from the [Scriptalicious][1] website. The post was posted in 2009 but it still valid and common script today.


> ## Redirect www to non-www:
> 
> ```
> RewriteEngine On
> RewriteBase /
> RewriteCond %{HTTP_HOST} ^www.yourdomain.com [NC]
> RewriteRule ^(.*)$ http://yourdomain.com/$1 [L,R=301]
> ```
> 
> ## Redirect non-www to www:
> 
> ```
> RewriteEngine On
> RewriteBase /
> RewriteCond %{HTTP_HOST} ^yourdomain.com [NC]
> RewriteRule ^(.*)$ http://www.yourdomain.com/$1 [L,R=301]
> ```
> 
> Both of these rules send a full search engine friendly 301 HTTP redirect. They also preserve the entire URL (so yoursite.com/about redirects to www.yoursite.com/about).

From [http://www.scriptalicious.com/blog/2009/04/redirecting-www-to-non-www-using-htaccess/][2]


▋Makzan • 兆康 • 晴

[1]: http://www.scriptalicious.com
[2]: http://www.scriptalicious.com/blog/2009/04/redirecting-www-to-non-www-using-htaccess/





