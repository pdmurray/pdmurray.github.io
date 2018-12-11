---
layout: blogpost
title: Running Jekyll on c9.io
categories: blog
name: jekyll-on-cloud-nine
---
I'm always trying to find easier ways to run my personal site.  For a long time, I was actually self-hosting out of a server in a closet at home.  That was a great way to learn more about hosting web applications on linux-- I first started experimenting with NginX, OpenSSL and DNS, because of it.  However, once I started learning about cloud hosting through AWS and Azure and the benefits those solutions provide, it started to become obvious that self-hosting was a bit inferior.
<!-- truncate_here -->
After testing the waters on both of those systems, I ended up setting up an Ubuntu VM on Microsoft Azure and migrating my site onto there.  Now I could easily clone the entire setup for backup purposes, or scale up or down as necessary with a few clicks (occasionally I like to run a Minecraft server on the same system).

Updating the jekyll site was still a bit of a process, though.  I was logging in to the system through ssh and doing my editing there and then manually doing a build, copying the files over to my NginX server directory, commiting the changes, etc.  I knew all along that GitHub actually directly hosts Jekyll projects on GitHub Pages (github.io), but I didn't want to give up the SSL (https://) capability I had baked in.  Some news came out that GitHub might consider supporting SSL with custom domains on github.io in the near future though, so I thought it might be time to try it out.

Now, the site is up and running on GitHub Pages, and I can't help feeling like I should have done this sooner.  It is now incredibly easy, I can work on a cloned repo anywhere or even directly on GitHub's markdown editor, and a simple push to master will immediately update the site.  Previewing changes in real-time while I'm editing still could be easier though.  Enter Cloud 9.

It's really surprising how well integrated everything is on the Cloud 9 platform.  Have a look:
![Cloud9 Dev Environment]({{ site.url }}/img/c9.png)
Now I can edit a new post, preview the markdown, run the jekyll server (with --watch so that it continously builds) and preview a live version of the site all in a *single browser window*.  The entire environment gets saved to my account and I can bring it up on any PC in a new browser window.  I highly recommend trying it out for jekyll/pages deployments.