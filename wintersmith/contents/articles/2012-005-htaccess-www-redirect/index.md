a quick note


The Apache Web server supports URL rewriting with the mod_rewrite engine. Placing custom rules in an .htaccess file lets you do all sorts of useful things to keep your URLs tidy. One really handy thing you can do for search engines and visitors is redirecting traffic from www to non-www version of your domain (and vice versa).


Some people prefer to use www.somesite.com, but some people prefer the shorter somesite.com. There isn't really a right or wrong way to do it, but whatever you choose you can make sure all of your visitors get sent to the same place. With a few simple rules on the server you can choose from non-www to www, or redirecting from www to non-www.

If you already have a file named .htaccess on your Website you can add to it. If not, create one (yes, include the period at the beginning). Add either of the following rules and save. Replace yourdomain.com with your actual domain name.

Redirect www to non-www:

RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} ^www.yourdomain.com [NC]
RewriteRule ^(.*)$ http://yourdomain.com/$1 [L,R=301]
Redirect non-www to www:

RewriteEngine On
RewriteBase /
RewriteCond %{HTTP_HOST} ^yourdomain.com [NC]
RewriteRule ^(.*)$ http://www.yourdomain.com/$1 [L,R=301]
Both of these rules send a full search engine friendly 301 HTTP redirect. They also preserve the entire URL (so yoursite.com/about redirects to www.yoursite.com/about).

Search engines can usually figure out which format is preferred, but since you're showing the same page for www and non-www URLs it can't hurt to be consistent about it.

Create your .htaccess rewrite code:

Use our www Redirect Generator tool to automatically generate the required redirect code.

http://www.scriptalicious.com/blog/2009/04/redirecting-www-to-non-www-using-htaccess/

