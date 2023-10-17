# MyBlog
This repository contains the structure for my [website](https://kamuench.github.io/blog/). This website is created with [Jekyll](https://jekyllrb.com/).
Which is a neat tool to create static websites, like a personal blog for instance.

It did all that on Windows via [Windows-Subsystem für Linux (WSL)](https://learn.microsoft.com/de-de/windows/wsl/about).

To use jekyll you have to install ruby and bundler. If you don't have a C or C++ compiler installed yet, you might want to do that first.  

Install compilers:
``` bash
apt-get install gcc
apt-get install c++
```

Install ruby:
``` bash
apt-get install ruby
apt-get install bundler
```

Now you are ready to install jekyll. You can follow the instruction at the official [Jekyll website](https://jekyllrb.com/).  

Install jekyll:
``` 
gem install bundler jekyll
```
---
Create new project:
```
jekyll new my-awesome-site
```  
---
Go into the directory of the newly created site and run the serve command to visit your new website:
```
bundle exec jekyll serve
```  
---
That's it 

