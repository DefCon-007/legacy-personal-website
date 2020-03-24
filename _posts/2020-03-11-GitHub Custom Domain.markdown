---
title: "Using custom subdomain with GitHub repositories"
layout: post
date: 2020-03-23
noMediumRedirect: True
image: /assets/images/octocat.png
headerImage: true
tag:
- GitHub
- Tech
category: blog
author: defcon
description: Markdown summary with different options
---


# Using custom subdomain with GitHub repositories

GitHub actually allows you to host websites for your projects directly from the repository itself. It will have URL something like `https://<username>.github.io` , you can add your custom domain to it too. If you haven’t done it, GitHub has pretty good documentation about it. You can read it [here](https://help.github.com/en/github/working-with-github-pages/about-custom-domains-and-github-pages).

Now, let's suppose you have already set up a custom domain and your default site is accessible through `https://example.com`. Now, if you create a new repository named project , and enable GitHub pages, it will be accessible through `https://example.com/project` but sometimes it makes more sense to have a custom sub-domain, like `https://project.example.com`. To do this, there are some additional configurations required. Just follow the steps below.<br/>


To make the steps more clear, I will use my own, recent project example for which I set up the custom subdomain. My GitHub username is DefCon-007 and my personal website which was available through GitHub pages at [https://DefCon-007.github.io](https://DefCon-007.github.io) is served from my custom domain with [https://defcon007.com](https://defcon007.com) and https://www.defcon007.com](https://www.defcon007.com). I now had a new repository named utilobot-website which contained some HTML and was served at [https://defcon007.com/utilobot-website](https://defcon007.com/utilobot-website) and I wanted it to be served at [https://utilobot.defcon007.com](https://utilobot.defcon007.com). 

## Step 1: Configure DNS settings

Go to your domain provider’s website and add a new CNAME record with name as your subdomain and value as your GitHub root URL with a trailing dot. In my case the name was `utilobot` and the value was `defcon-007.github.io.` The dot at the end is not a typo!

![Cloudflare DNS entry screenshot](/assets/images/blog/github_custom_domain/cloudflare.png)*<center>Cloudflare DNS entry screenshot</center>*

## Step 2: Add CNAME file

Now, add a new file named CNAME to your repository with just a single line in it, that is your complete URL. 

![UtiloBot CNAME file](/assets/images/blog/github_custom_domain/cname.png)*<center>UtiloBot CNAME file</center>*

You can also go to the repository settings and enter your custom domain in the GitHub Pages section, it will automatically add the CNAME file. 

That’s it, you have a custom domain for your GitHub project now. Try opening it with http first, and it is working fine, you can select Enforce HTTPS option in the repository settings page. 

## Troubleshooting

1. If the custom sub-domain does not work, try after some time, so that the DNS records are propagated, also try removing the trailing period from the URL in step one, it works sometimes.

1. If you find that the Enforce HTTPS checkbox is disabled, and your custom domain is working fine with http , try deleting the CNAME file, push the changes, create the same CNAME file with the same content and push again. It should be enabled now. 

Thanks for reading.
