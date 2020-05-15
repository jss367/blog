---
layout: post
title: "VSCode Tips"
tags: [Software]
---

One of the most important things to be able to do in VSCode is to open the command palette. From there you can access the settings:

  * Open the Command Palette: `CMD/CTRL + SHIFT + P`
  * You can use either the User Interface (`Preferences: Open Settings (UI)`) or edit the JSON directly `Preferences: Open Settings (JSON)`. 
    * You can also jump to the settings or Command Palette by clicking on the settings wheel in the bottom left corner.
* You can see (and copy) all the extensions and settings I use in my [Visual Studio Code Settings Sync Gist](https://gist.github.com/jss367/6574f6940f7c9603ffd949f42ca4f205)


User settings are not stored in the project. Instead, they are at: C:\Users\Julius\AppData\Roaming\Code\User\settings.json


In the `launch.json` file, you can either use full paths or relative paths:

"program": "/full/path/to/python_trainer.py",
            
or 

"program": "${file}",

Cool hot keys:

Zen mode: Ctrl+K Z
(So hold control and hit "k", then let go of both and hit "z"). Double tap "Esc" to escape.