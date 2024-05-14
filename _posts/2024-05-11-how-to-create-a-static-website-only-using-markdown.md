---
layout: post
title: How to create a static website only using Markdown
categories: how-to
---

In this blog, you'll learn how to create a static website by only using Markdown

To do this, we'll use Jekyll

Jekyll is a static site generator that allows us to write our posts in Markdown and transform it into HTML code

To start things off, we need to define where your website will start

For that, you need to create a ```index.md```

Now, to define how Jekyll will run, you need to create a ```_config.yml```

In the ```_config.yml```, you'll define your title, your description, and most importantly, your theme

I use ```Minima``` so most of their documentation are in their <a href="https://github.com/jekyll/minima/blob/master/README.md" target="_blank">README</a>, explaining how their plugins work, how to include icons that redirect to your social media and stuff like that

There are a lot of Jekyll themes that Github makes available, to check them out access their <a href="https://pages.github.com/themes/" target="_blank">website</a>

```bash
title: My Personal Blog Website
description: This is my simple blog website where I can host my stuff for the time being
theme: minima
```

To start things on ```Minima```, you need to set the ```index.md``` to have the home layout
```bash
---
layout: home
---
```

To create a post on Minima, you need to create a folder called ```_posts```

Inside of the folder you created, you'll follow this naming model ```<year>-<month>-<day>-<filename>.md```

## How to create a domain on Github Pages

To create a Github Pages domain, you first need to create a Github account

Then, create you own repo for hosting the Github Pages domain

After that, go to Settings and then Pages

In Pages, you must set the branch from ```None``` to ```main``` and save it

To access your Github Pages domain, just type ```<your_username>.github.io/<repo_name>```

## How to run your Jekyll website locally

First, you need to install Ruby on your computer

To install it, go to this <a href="https://jekyllrb.com/docs/installation/" target="_blank">website</a> and install according to your operational system

Follow their guide step by step

Afterwards, create a file called ```Gemfile```, there you're going to put all the themes from Github Pages, so it doesn't render any incompatibility

```ruby
source "https://rubygems.org"

require 'webrick'

gem "github-pages", group: :jekyll_plugins
```

On the ```terminal```, run this command to install all themes
```bash
bundle install
```

To run the website, run this command on the terminal
```bash
bundle exec jekyll serve
```

To access it, just run ```localhost:4000``` to view your website

## How to make your website similar to mine
Just fork my website <a href="https://github.com/marshfellow42/Markdown-Blog-Website" target="_blank">repo</a>

To edit the footer, just go to ```_includes``` and there you're going to find a file called ```footer.html```

To edit anything else, just go there and edit the files for your needs