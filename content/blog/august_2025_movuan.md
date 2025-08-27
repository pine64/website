---
title: "Project Showcase: Movuan"
date: "2025-08-26"
authors: ["Caffeine"]
categories: 
  - "community"
  - "news"
  - "pine64-community"
tags: 
  - "project showcase" 
cover: 
  image: "pine64_banners/community/pine64_red_movuan.png"
images:
  - "/blog/images/pine64_banners/community/pine64_red_movuan.png"
summary: "A showcase of the Devuan based operating system for the PinePhone called Movuan."

---

![Blog post banner artwork](/blog/images/pine64_banners/community/pine64_red_movuan.png)

{{< toc >}}

## The Movuan project
The Movuan project was started by community member [lxb](https://gitlab.com/l2385) as an alternative to mobile distributions using the systemd init system. Thanks to being forked from Mobian, the project uses modified Mobian debos to build it's images. 

There is an [optional script](https://gitlab.com/l2385/movuan/customizing-movuan-under-host-mounting) which can customize a Movuan image to install extra software like AndroidImpEx for importing contacts and sms messages from an Android phone, Ungoogled Chromium, local caching DNS (bind) tunnelled through TLS (stubby) to privacy minded servers and an inbuilt adblocker through a caching proxy (squid).

![Movuan Terminal](/blog/images/August_2025/movuan_1.png)

![Movuan Logo](/blog/images/August_2025/movuan-logo.png)

### Installing Movuan
Movuan offers an image based on Devuan 5.0 (Debian 12) with Phosh. Users can find Movuan images in the [GitLab repository](https://gitlab.com/l2385/movuan/movuan-recipes/-/releases) along with [instructions on installing said image](https://gitlab.com/l2385/movuan/movuan-recipes#install). As usual you can use a tool like Balena Etcher or Gnome Disks to write them to an SD Card as well. 

You may build your own images as well [using the debos recipe in the GitLab repository](https://gitlab.com/l2385/movuan/movuan-recipes#prepare-your-build-system). 

![Movuan Phosh home screen](/blog/images/August_2025/movuan_2.png)

### What is Devuan?
Devuan for users who are unaware is a fork of Debian which provides alterative init systems to Systemd such as:
* sysvinit (default)
* openrc
* runit
* sinit
* s6
* shepherd

The benefit of using a different init system depends on the features it offers over another. So it is highly depends on user preference. Other than this change it runs the same (at a surface level) as Debian/Mobian. 

Users can learn more about the Devuan project [here](https://www.devuan.org).

### Future goals and contributing
The goal of the Movuan project is to merge into Devuan as an official version, but it still requires some polishing to do before this can happen. Specifically help with packaging and testing would be appreciated! If anyone is interested in helping with this project can contact lxb1@yahoo.com.

## Do you have something to share?
Do you have news to share with the community? You can have your news posted on this blog by heading over to [this tutorial and following the template](https://pine64.org/documentation/Introduction/Writing_a_blog_post/). All community updates are written in markdown which you can learn how to write [here](https://www.markdownguide.org/basic-syntax/).

If you get stuck, feel free to ask the folks in chat by finding your respective chat platform at https://pine64.org/community/.

## Contact 
### Community
Feel free to contact me if you have any concerns about community related topics. This can be about getting project support, sharing project updates, prolonged wait times for support from PineStore (anything after 1-2 weeks) and any general feedback that could help improve the community. 

Community manager: camden.b@pine64.org

### PineStore
**If you have quality control issues with your device once you receive it, don't wait, contact PineStore support.**

* For general queries and information from the Pine Store: info@pine64.org
* For queries regarding support from the Pine Store: support@pine64.org
* For sales/wholesale related questions: sales@pine64.org