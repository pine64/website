---
title: "A new design"
date: "2023-04-13"
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "community"
cover: 
  image: "rebrand_large.png"
---

![](/blog/images/rebrand_large.png) 

As it was teased with the March update and the December blog post of last year, there is a community website redesign being worked on. Launched at https://beta.pine64.org/ we're proud to give a very early insight of what the redesign currently looks like.

To give a warning in advance, in this preview of the redesign, you will find a lot of unfinished parts, run into issues and maybe there are things you liked at the old (current) page more. That's what the beta launch is for. While the old website was run on Wordpress and maintained by a handful of people, the idea of the new community website redesign after being started as a project of a single person is, that everyone can contribute to the community website. That's why the redesign is launched early: to gather feedback, to gather ideas and to involve everyone interested in contributing so that there will be a nicely working website available later.

## Some technical details

To give an insight into some technical details: 

The former website was running on Wordpress. While easy to use, this also means there was a lot of heavy Javascript, connections to third-party websites (like Google fonts) constantly had to be prevented by adjusting site settings and if people found typos in the blog post then admins had to be asked to fix them. 

The redesign tries to go a different way. It uses [Hugo](https://gohugo.io/) ("The world’s fastest framework for building websites") and it creates static html pages from content formats such as Markdown, Pandoc and AsciiDoc (see [Hugo - Content Formats](https://gohugo.io/content-management/formats/) for the supported formats). In fact this blog post you are reading is written in Markdown - show and edit this blog post under [a_new_design.md](https://github.com/pine64/website/edit/content/blog/a_new_design.md).

![](/blog/images/rebrand_structure.png)

The redesign tries to avoid using Javascript as much as possible. Javascript is currently only used on the front page to click between the slider images, as well as the YouTube preview (more about this below). The slider will work just fine with disabled Javascript.

There are no CDNs used in the redesign. No Google Fonts, no externally hosted podcast player, no analytics, no non-sense. The author also wrote a two-click solution for YouTube embeds. This means there is no longer a YouTube iframe directly in the blog post, which connects to Google as soon as opening the blog post even without watching the video. Instead there is no connection made to Google until the user clicks on the video preview. The video preview is generated and stored locally on the server.

![](/blog/images/rebrand_youtube.png)

Try it in the blog post "[March Update: Tablet Bonanza!](/2023/04/01/march-update-tablet-bonanza/)".


## The logo challenge

Together with the beta redesign, there is also the [logo challenge](/contests/the-logo-challenge/) started to get input from everyone regarding a new logo. The logo you see here is a preliminary draft to show, how the logo could look like. On top is the current logo, on the bottom is the new draft.

![](/blog/images/rebrand_logochallenge.png)

Please read the thoughts in the [logo challenge](/contests/the-logo-challenge/) and bring your best thoughts and ideas.

## Documentation

There is also a [documentation](/documentation/) tab added in the navigation menu above, as you might have noticed. The documentation pages are currently all PINE64 wiki articles parsed into AsciiDoc files. AsciiDoc is used due to the greater flexibility than Markdown but both or any of the above mentioned content formats can be used and even mixed. The documentation pages are currently in **early alpha**. 

To not get into the boring details too much, the Mediawiki articles from https://wiki.pine64.org are basically getting parsed and written into AsciiDoc files without too many changes. Most of the current issues in the documentation pages (wrong order of articles, non-working links, missing templates, broken tables and more) can be fixed easily. The reason why they are not fixed yet is because it is hard to maintain two documentation pages at the same time, the docs and  the wiki. Especially while working alone on the redesign it was decided to dynamically parse the wiki instead for now, so that the author does not have to manually apply every change made to the wiki to the docs as well. 

To give some numbers, the custom parser alone is curently almost 500 code lines long, the rule yaml to write the documentation targets is another 500 lines and the rule yaml for separating long articles into multiple documentation pages is over 1500 lines long. So it would be very surprising if everything works flawlessly. There are currently over 250 documentation pages written. The issues in the docs will all be ironed out before a launch.

For the docs there are new shiny board images created and they will be used everywhere to make explaining hardware functionality easier. Here is for example the Ox64 pinout image as created as part of the docs:

![](/blog/images/rebrand_ox64.png)

As part of the new documentation, the author also made a lot of changes to many wiki pages. Updating old information, simplifying old structures, writing new articles, to bring everything information in a more up-to-date and modern state. The author wants to underline that users should not be worried, the wiki doesn't go away. In fact it is a great place for users to document their projects, bringing a strong tie between the community members, the community website and their contributions.

## Contributions made easy

Hugo also has one nice advantage. Changes to the website can be previewed easily on your computer, making it very easy for new contributors to find out how everything is working and if their changes work as intended. To give a short overview of the steps:

Clone the repository of the website:

```
git clone https://github.com/pine64/website/
```

Then change the directory into the folder:

```
cd website
```

And then preview the website using:

```
hugo server
```

It's super simple!

![Hugo usage](/blog/images/rebrand_hugo_usage.svg)

The complete process is explained in details under https://github.com/pine64/website/ and we're happy to help in the [community chat](/community/).

The project is structured the following:

```
website/
├── archetypes/
│   └── default.md
├── assets/
├── config/_default/
│   └── config.toml [site configuration]
├── content/
│   │── blog/
│   │── community/
│   │── contests/
│   │── documentation/
│   └── podcast/
├── data/
├── layouts/
├── public/ [contains the html files]
├── static/
└── themes/pinetheme/
    │── archetypes/
    |   └── default.md
    │── layouts/
    │── static/
    │   │── artwork [background artwork]
    │   │── css [css files]
    │   │── img [static images]
    │   │── js [static javascripts]
    │   │── podcast [podcast episodes]
    │   └── podlove [podcast player]
    └── theme.toml [theme configuration]
```

For an explanation of the folder structure see https://gohugo.io/getting-started/directory-structure/.


## Outlook

With the upcoming redesign of the community website and the possibility for everyone to contribute to it, the community is going the next step and it ultimately becomes one step more open. 

The *Hugo* framework opens us up a lot of different possibilities, including multi-language pages. If community members are interested in this any many more features we're eager to see the ideas and your contributions!