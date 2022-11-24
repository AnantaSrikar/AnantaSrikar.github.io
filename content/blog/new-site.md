+++
author = "Ananta Srikar"
title = "New site!"
date = "2022-11-22"
description = "Blog - Deployment "
tags = [
    "new-site",
    "deployment",
]
+++

After months of procrastination, I finally decided to abandon my old site which was built all the way from scratch. It got too difficult to manage the site, which in turn demotivated me from making more blogs. Hence I decided that it was time to move on, and choose a Hugo theme to continue my site.

After sifting through all the available themes, [Hugo Coder](https://github.com/luizdepra/hugo-coder/) was the most appealing. I quickly cloned it, modified the config file, and pushed it to GitHub. However, I had to set up the automation for building and deploying my site.

Fortunately, GitHub actions had the perfect solution. It recommended the `Deploy Hugo site to Pages` workflow. I immediately added it and hit deploy, for my beautiful site to come online... but my domain name was broken.

After debugging for a while, I figured out that I had to 'unlink' the domain name from my old website repo so that the new repo can use it. Once that was done, the site was finally live. 

With this online, blogging will be much easier. Which means you can expect more blogs. Yaay!

Until next time,\
Srikar