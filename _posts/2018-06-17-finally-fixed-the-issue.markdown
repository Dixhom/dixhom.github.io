---
layout: single
title:  "finally fixed the issue"
date:   2018-06-17 22:26:16 +0900
categories: category1
---

The issue was below.  

[ruby - Jekyll remote theme doesn't work locally - Stack Overflow](https://stackoverflow.com/questions/48728510/jekyll-remote-theme-doesnt-work-locally/50403126#50403126)

I got things work by [Matt's answer](https://stackoverflow.com/a/50403126/4061339).

> aaaah I was just bashing my head against this as well. I ran bundle exec jekyll serve --verbose and saw that jekyll-remote-theme was never being initialized at all (each plugin logs a Requiring: jekyll-<thing> line). Then I noticed this block in the Gemfile:
> 
> # If you have any plugins, put them here!
> group :jekyll_plugins do
>   gem "jekyll-feed", "~> 0.6"
> end
> I added "gem jekyll-remote-theme" to that plugin block and that fixed it – doh!
> 
> There are a few notes in the jekyll changelogs about this Gemfile group, but I didn't find any of it super helpful in explaining what's going on here.
> 
> hope that helps!

Many thanks, Matt!