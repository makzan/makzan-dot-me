title: Host wintersmith static website on Heroku
author: Makzan
date: 2012-09-12 23:40
template: article.jade

I want to host wintersmith generated static website on Heroku and face one problem.

## Problem
A Wintersmith project is in following folder hierachy. There are folders and files for the logic and content. All I want is to put the output folder as public on Heroku. It will be strange if we put the default Wintersmith site hierachy.

```
Wintersmith Site
├── config.json                          
├── build                       <- The output folder that we put public.
├── contents
│   ├── archive.md
│   ├── articles                         
│   ├── authors                          
│   ├── css
│   │   ├── github.css
│   │   └── main.css
│   ├── feed.json            
│   ├── index.json
└── templates
    ├── archive.jade
    └── layout.jade
```

## Solution

This is the setup I use to host a wintersmith static websites on Heroku.

### Arrange the folders

I put all the wintersmith logic file into a folder named `wintersmith`. Then set the build output folder to the root of the site folder.

```
Current Site
├── .slugignore
├── Rakefile
└── wintersmith
    ├── config.json 
    └── contents
          ├── archive.md
          ├── articles                         
          ├── authors                          
          ├── css
          │     ├── github.css
          │     └── main.css
          ├── feed.json            
          ├── index.json
          └── templates
                ├── archive.jade
                └── layout.jade
```

### Rakefile to make life easier

For the ease of operation, I wrote a Rakefile for the common preview, build, push operation. I can just build the files with `rake build` and push the output files to heroku with `rake push`.

<script src="https://gist.github.com/3707395.js"> </script>


### Ignoring the wintersmith logic and data files on Heroku

Also there is a `.slugignore` file to ignore the Rakefile and wintersmith folder on Heroku.

```
wintersmith
Rakefile
```
　

▋Makzan • 娜菲 • 晴