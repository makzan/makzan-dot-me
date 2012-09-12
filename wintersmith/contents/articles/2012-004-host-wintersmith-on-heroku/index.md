title: Host wintersmith static website on Heroku
author: Makzan
date: 2012-09-12 23:40
template: article.jade

<script src="https://gist.github.com/3707395.js"> </script>

This is the setup I use to host a wintersmith static websites on Heroku.

I put the wintersmith files into a folder named 'wintersmith' and put the output files in git root directory instead of subdirectory. Then a .slugignore file to ignore the wintersmith logic folder.

In this setting, I can just build the files with `rake build` and push the output files to heroku with `rake push`.

　

▋Makzan • 娜菲 • 晴