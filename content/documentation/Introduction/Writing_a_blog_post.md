---
title: "Writing a blog post"
draft: false
menu:
  docs:
    title:
    parent: "Introduction"
    identifier: "Introduction/Writing_a_blog_post"
    weight:
---

This guide is for community members wanting to announce project updates on the Pine64 community blog.

## Setup
You should first prepare a fork of the [pine64 website repository](https://github.com/pine64/website) on GitHub, then clone it. 

`git clone https://github.com/pine64/website.git`

Once the repository is cloned, you can open up the template folder at `/content/blog/template` and copy and rename `template_update.txt` to `/content/blog` as a `.md` file. 

{{< admonition type="important" >}}
 **Heads up**, try to keep the naming of blog post files consistent. Put the month and year and a brief description of the contents. For example:  `august_2025_pt2_factory_image.md` and `december_2020_pinephone_release.md`. 
{{< /admonition >}}

## Blog post details

Once the template is copied you can start editing the blog post details. Below is an example of a blog posts basic layout with some explanations of what everything does.

{{< figure src="/documentation/images/blog_tutorial/layout_explanation.png" width="600" >}}

* The title should be formatted like "Project Update: PineTab2 Arch Linux Update" or "Project Update: PinePhone Pro FreeBSD port"
* The date entry follows the yyyy-mm-dd format. Make sure to test that the blog post appears in the hugo preview, depending on your timezone you may have to set it a day back.  
* Categories are already correct in the template, so leave these alone. 
* Tags are used to recommend similar blog posts with the same tags. For example: `pinetab2`, `pinetab-v` and `pinenote`.

{{< admonition type="important" >}}
**A useful tip**, if you find yourself stuck with what what to put in the details at the top of the file, there is a completed example in the templates folder.
{{< /admonition >}}

## Cover art details

There are a few different cover artworks to choose from that are included at `/content/blog/images/pine64_banners`. The default image is called `pine64_blue.png` and has green, yellow and red color variations at `pine64_banners/pine64_colors`.

### Blog post list cover art

The first option is `cover: image:` which is used for the cover image found on the blog post list. The image path for this option starts with the `pine64_banners` folder. 
* `pine64_banners/festival_lights.png`
* `pine64_banners/pine64_colors/pine64_yellow.png`

{{< figure src="/documentation/images/blog_tutorial/blog_list.png" width="400" >}} 

### Embed cover art

The second option is `images:` which is the embed cover image. This image will appear when you post the link on platforms like Mastodon and Matrix. The image path for this option starts with the `/blog` folder. 
* `/blog/images/pine64_banners/festival_lights.png`
* `/blog/images/pine64_banners/pine64_colors/pine64_yellow.png`

{{< figure src="/documentation/images/blog_tutorial/embed.png" width="400" >}}

### Blog post cover art 

The final option is found after the end of the blog post options which is the cover artwork found in the blog post itself. The image path for this option starts with the `/blog` folder. 
* `![Blog post banner artwork](/blog/images/pine64_banners/festival_lights.png)`
* `![Blog post banner artwork](/blog/images/pine64_banners/pine64_colors/pine64_yellow.png)`

{{< figure src="/documentation/images/blog_tutorial/post_cover.png" width="400" >}}

## Write
After all this setup is done you are ready to start writing. Blog posts are written in Markdown so it is expected that you take a look at the [Markdown syntax guide](https://www.markdownguide.org/basic-syntax/) if you haven't already. If you are unsure on how to lay out your blog post take a look at some previous updates 

## Install hugo 
You can preview what the final post will look like by installing the hugo site generator. On Linux it's straight forward, use your package manager to install `hugo`. 
* Fedora: `sudo dnf install hugo`
* Debian/Ubuntu: `sudo apt install hugo`
* Arch Linux: `sudo pacman -S hugo`

On Windows you must download the binary and add it to your environment variables, you can find prebuilt binaries [here](https://github.com/gohugoio/hugo/releases). For any other operating systems and installation information you can find the documentation [here](https://gohugo.io/installation/)

## Test your blog post
start the hugo site generator by running `hugo server` in the root of the website repository then check for anything that may look off in your blog post.

## Merge that thing!
Once you're happy with what you've written, you can submit a pull request on the [website repository](https://github.com/pine64/website) and we will take a look and review it when we are able. 

## Available cover art
For those who are interested in making their own, the source files for the following cover artworks have been placed in the `/content/blog/images/pine64_banners/source_files` folder. Make sure to not overwrite the originals. 

**pine64_blue.png (default)**
{{< figure src="/blog/images/pine64_banners/pine64_blue.png" width="400" >}}

**festival_lights.png**
{{< figure src="/blog/images/pine64_banners/festival_lights.png" width="400" >}}

**the_sign.png**
{{< figure src="/blog/images/pine64_banners/the_sign.png" width="400" >}}

**forest.png**
{{< figure src="/blog/images/pine64_banners/forest.png" width="400" >}}

## Bring your own cover art
If you'd like to bring your own cover art for your blog post, you can drop it into the `/content/blog/images/pine64_banners/community` folder. Make sure to edit the path for the cover art at the top of the blog post document to reflect this.