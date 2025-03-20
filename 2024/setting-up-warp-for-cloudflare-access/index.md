---
title: "Setting up WARP for Cloudflare Access"
date: 2024-12-14
categories:
  - "Tutorials"
tags:
  - "dev"
coverImage: "./images/cloudflare-hero.webp"
public: true
---

Cloudflare Access puts your Cloudflare app behind another layer of authentication.
For example, you can require a user to authenticate
before accessing the admin URL of your blog.

To make the authentication process easier,
you can set up Cloudflare WARP so that you are automatically authenticated.

This tutorial assumes that you already have a Cloudflare account
and have finished Cloudflare Zero Trust onboarding.

Set up device enrollment permissions to restrict
who can log in to your Zero Trust account.
In Cloudflare Zero Trust, go to _Settings_ → _Device enrollment permissions_
and add a new rule in the _Rules_ tab.
For me I will just allow my email address.

See the full guide [here](https://developers.cloudflare.com/cloudflare-one/connections/connect-devices/warp/deployment/device-enrollment/)

<figure>

![](images/Screenshot-2024-11-23-at-10.06.49.webp)
<figcaption>
Device enrollment permissions
</figcaption>
</figure>

You can then connect to Zero Trust.

![](images/Screenshot-2024-11-23-at-10.25.36.webp)

Also make sure to enable _WARP authentication identity_ in your Cloudflare Access app.

![](images/Screenshot-2024-12-14-100318-1.webp)

You should now be able to access your Cloudflare Access app
without the need to manually log in to Cloudflare Zero Trust.

Image credit: [Abstract Line Pattern Vectors by Vecteezy](https://www.vecteezy.com/free-vector/abstract-line-pattern)