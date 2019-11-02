---
title: "Git: Fatal Protocol 'Https' Is Not Supported"
date: 2019-11-02T13:18:35+07:00
draft: false
description: "A really confusing problem with really simple solution."
categories: ["other"]
displayInMenu: false
displayInList: true
resources:
- name: featuredImage
  src: "Git Fatal Protocol Https Is Not Supported.png"
  params:
    description: "git fatal protocol https is not supported"
---

Today, I got an error stating "Git: Fatal Protocol 'Https' Is Not Supported" while I was trying to clone this blog repository from github to my Windows local machine. So, what I was trying to do was double-checking the command and it still didn't work.

Fortunately, I found a solution to this problem on stackoverflow. Therefore I want to share this to you in this blog. See, for more detail: <https://stackoverflow.com/questions/53988638/git-fatal-protocol-https-is-not-supported/55324351>.

Well, the solutions are:

1. Type full command without copy-paste.
2. If you want to use copy-paste functionality, don't use Ctrl+v keyboard shortcode, use right-click mouse and select paste option instead.

Okay, it works as expected! So, what's the problem?
The thing is, when you try to paste for example URL of github repository with Ctrl+v shortcut, your terminal prepend hidden character before https protocol which is not understandable by git.

I think that's pretty much for now. If you're still facing problem, please comment in the section below.

**K.Kusumo**
