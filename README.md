# hasper

Hasper is a port of [Ghost's](https://ghost.org/) casper theme for the [Hugo](https://gohugo.io) static-site generator. It hopes to get you from zero to beautiful with minimal effort.

## Installing

If you haven't yet installed Hugo, make sure to follow [these instructions](https://gohugo.io/overview/quickstart/) first to install the hugo binary as well as setup your site directory. 

Once you're done, simply clone this repository into the `themes` subdirectory of your site folder:

`cd /your/site/directory/themes; git clone git@github.com:dencold/hasper.git`

...and you can start using the theme immediately:

`hugo server -t hasper`

## Sample Configuration

Here is a sample configuration for a fictional Baywatch enthusiast site:

```yaml
---
baseurl: "http://baywatch.com/"
languageCode: "en-us"
title: "Memories of Baywatch"
paginate: 5
Copyright: "All rights reserved - 2016"
canonifyurls: true

params:
  description: "David Hasselhoff loves telling you about Baywatch."
  cover: "images/cover.jpg"
  author: "david"
  logo: "images/logo.png"
  googleAnalyticsUserID: ""
  RSSLink: "http://feeds.feedburner.com/..."
  githubName: "thehoff"
  twitterName: "thehoff"
  hideHUGOSupport: false

author:
  david:
    name: "David Hasselhoff"
    bio: "Don't Hassle the Hoff"
    location: "Baltimore, MD"
    thumbnail: "images/avatar.jpg"

menu:
  main:
    - name: "Blog"
      weight: -120
      identifier: "blog"
      url: "/"
    - name: "About"
      weight: -110
      identifier: "about"
      url: "/about"
```

## Configuring Multiple Authors

You can add as many authors as you like under the `author` section of the `config.yaml`. In the example above, we just had one author, David Hasselhoff, here's how we could add Pamela to the blog roll:

```yaml
author:
  david:
    name: "David Hasselhoff"
    bio: "Don't Hassle the Hoff"
    location: "Baltimore, MD"
    thumbnail: "images/avatar.jpg"
  pamela:
    name: "Pamela Anderson"
    bio: "Little known fact, I am vegan"
    location: "Canada"
    thumbnail: "images/pamela.jpg"
```

You can now reference either "david" or "pamela" on the author attribute of a post's [front-matter](https://gohugo.io/content/front-matter/) and their information will automatically get pulled in by hugo.

## Attribution

Hasper was originally [a fork](https://github.com/dencold/hugo-theme-casper) of the [hugo-theme-casper](https://github.com/vjeantet/hugo-theme-casper). This version has been updated with the following improvements: 

* author thumbnail fixes across the site (original version only worked on list template): 25467fc92ca611ae7a6d517c16b47cdac0ae9dcb
* switching from bespoke `.Site.Data.Author` in favor of Hugo's canonical `.Site.Author`: 25467fc92ca611ae7a6d517c16b47cdac0ae9dcb
* icon aesthetic improvements, previous styles had ugly underlines: 22380914098cbf0dad119be18d7727521f097a29
* removing unused `page` directory which contained duplicate code: 8c2f9e8c5b138d89e1b5e2c39d2d6210c928ad9f
* allowing for external image linking (gravatar, twitter, etc), original theme hardcoded site's base url: 06afad23845e6e51c0ac55cef29c2e7caf7878d5
* share icons are now user-configurable: b334fed9c5e88447b98e5908c362f3d165e1ee02

