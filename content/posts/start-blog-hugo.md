+++ 
date = "2020-05-31"
title = "Starting a blog on Github Pages using Hugo"
slug = "start-blog-hugo" 
tags = ["blogging", "how-to"]
categories = []
series = []
+++

## Website on Github Pages

Traditionally, website building has always been about writing HTML, CSS and Javascript. But it all changed when static website generators came into being. Now you can write your website in markdown or any other fancy stuff and it automatically gets converted into a website (with html and css).

### Github Pages and Hugo

Github allows to host static website using Github Pages, i.e., you can set-up a static website and need not worry about hosting. Other than Github Pages, you can use [Netlify](https://www.netlify.com/), [Surge](https://surge.sh/) among others for static hosting.

Hugo is a static website generator, similar to Gekyll, which allows you to write web-pages/ blogs in Markkdown. It has a large number of templates too; thus you can customize it a bit, and focus on getting your ideas out.

## Setting it up

### Getting Started

This post is going to be about how I set up my website using Hugo template. To set-up hugo on your system, head down to (hugo guide)[https://gohugo.io/getting-started/quick-start/] on how to ready your system for it. If you want to try it via, docker, heaad down to the next section.


1. Create <yourusername>.github.io repository on Github and clone it on your system. 
2. Create a folder called `themes` in the cloned folder and clone the theme that you want to use. For me it was `git clone xyz`. 
3. From the `exampleSite` folder, copy everything to the base folder.
4. Make changes in the config.toml according to changes that suit you. 
5. Change the base URL to `"https://<yourusername>.github.io/public/"`.
6. In the content directory, make changes to about.md, contact.md and projects.md
7. Type `hugo` on command line to generate files.
8. Copy all the html and xml files generated in public folder to base folder. This is because base folder when github Pages opens your website is `<yourusername>.github.io/` and not `<yourusername>.github.io/public`.

### Setting up using Docker

Hugo is built on top of Go. The more simpler way is to install using the binary. But for people like me who don't want to install the binary either, Docker is super handy.

If you are on Windows system, this section would be super handy for you.

1. Download the Dockerfile and save it in the root folder (where you have your hugo files).
2. To build the Dockerfile, type `docker build -t hugo:cs .`
3. To run the Dockerfile, i.e., generate the website (Step 7), type `docker run --rm -v "${PWD}:/src" hugo:cs` in terminal. This will generate the website for you. 
4. If you want to see your website in action, you can preview it by typing `docker run --rm -it -v $PWD:/src -p 1313:1313 hugo:cs server -w --bind=0.0.0.0`. While viewing it in your browser at localhost:1313/public, make sure you replace `localhost` by the IP address of your Docker daemon if you are on Windows 10 Home. 


Got any suggestions or ideas, [hit me up](/contact).