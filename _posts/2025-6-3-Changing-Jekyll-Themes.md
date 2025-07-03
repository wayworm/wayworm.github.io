---
layout: post
title: Changing Jekyll Themes
tags: [Jekyll, theme-migration, GitHub Pages, static-sites]
---

Today I migrated this blog from using [the Jekyll theme called jekyll-now](https://github.com/barryclark/jekyll-now) to another, 
[Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy).

 **The simplest way to do this is forking the repository of the theme you want to use.**

I went through a bit of pain trying to set this up, as I was having trouble getting GitHub Actions to deploy the site. 
The cause of the issue is that my previous **jekyll-now** repo, was being hosted by pages. I'd suggest if you want to try out a few different themes,
then you should **delete your repo containing your site first**, before *forking the repo of the theme* you wish to use. Be sure to take out any content files such as blog posts first, Personally I'd suggest keeping them in a local folder seperate from your site's files, and copying your files over every so often, coupled with a seperate cloud storage e.g. Google Drive, Dropbox. 

Something like this should work for your local copy, it could run daily, weekly etc.:

### Linux
```bash
mkdir -p ~/my-blog-backup
cp -r _posts ~/my-blog-backup/

```

### Windows
```batch
mkdir %USERPROFILE%\my-blog-backup
xcopy _posts %USERPROFILE%\my-blog-backup\_posts /E /I
```
## Tutorial

[This video](https://www.youtube.com/watch?v=m1RYsmOMPLs) is a **very good tutorial** on setting up your own to at least build and deploy.

I hope this helps!

