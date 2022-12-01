+++
author = "Ananta Srikar"
title = "Space Invaders - PyGame"
date = "2020-01-14"
description = "Project - Deployment in Progress"
tags = [
    "game",
    "gamedev",
    "python",
]
+++

With the amount of Python code I had written for my [DiscordBot](https://github.com/AnantaSrikar/DiscordBot), I became somewhat confident about my understanding of Python. Besides that, my seniors keep saying that "one can do anything in python!" or so I was told. Since we can do anything, I thought why not try making a game?

Hence, I made a basic replica of the "Space Invaders" game in Python, using the `PyGame` library. I learnt all the basics of the grid and object movement. I downloaded various assets to display the spaceship, its bullets and the enemies. I figured out the logic for a bullet hitting the enemy and the deletion of the enemy object upon collision. At this point, it started to look pretty good!

I finally added random enemy generation, a score counter and sound effects. At this point I decided it was close to perfect and started looking for ways to package the project to send it to my friends. I tried both `cx_Freeze` and `PyInstaller` to create a packaged executable. `cx_Freeze` seemed to work. I used it to create an `.exe` which I sent to my family and friends to try!

**Tools used:** Python, PyGame library\
**Project type:** Hobby\
**Links:** [Project](https://github.com/AnantaSrikar/Space_Invaders)