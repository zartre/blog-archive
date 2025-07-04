---
title: "Migrating from WordPress to Astro"
date: 2025-06-29
categories:
  - "Thoughts"
tags:
  - "dev"
public: true
---

I have finally made the decision to move my blog from WordPress to Astro.
I had been thinking about this for some time but this weekend was
when I made the decision.

Some days ago the server for my blog ran out of bandwidth and I could
not even log into the control panel because of that; the account was
disabled. It only had 1 GB of monthly bandwidth because it's a small
site.

This raised the concern that I could not access _my_ content.
It was like I had lost the ownership in my content.

Migrating to Astro was easy. My homepage was already built with Astro
so I only had to add my blog posts into it and add some new pages
for the posts to live. Since I already had a copy of my blog posts in
Markdown stored on Github, I just had to add this repo into my Astro
site as a Git submodule.

The process took one day to complete (half day for two days); it was
quicker than I'd expected. This includes the effort taken to migrate
from Cloudflare Pages to Cloudflare Workers, and to redirect the old
URL to the new one (`http://blog.zartre.com` to `http://zartre.com/blog`).
Moreover, it was fun! Cloudflare makes it easy to deploy just about
anything they offer.

If you are starting a blog and has some knowledge in frontend website
development, I recommend you build it as a static site so that it can
be a project to practise coding. Above all, it means you own your
content, and as plaintext files that will not depend on any app to open.

See the source code here: https://github.com/zartre/zartre-2024
