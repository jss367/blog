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

You can do `CMD/CTRL + P` to open up search. And just add `>` to the bar to make it the command palette.

User settings are not stored in the project. Instead, they are at: C:\Users\Julius\AppData\Roaming\Code\User\settings.json


In the `launch.json` file, you can either use full paths or relative paths:

"program": "/full/path/to/python_trainer.py",
            
or 

"program": "${file}",

## Key bindings

Ctrl k to open key bindings. From there many things are just one button, such as `z` for zen mode.

If you just hit control + k it brings up a list of key bindings, which you can customize.

Zen mode: Ctrl+K Z
(So hold control and hit "k", then let go of both and hit "z"). Double tap "Esc" to escape.


Autoformat:

Mac: Option + Shift + F



Clean up imports:

- allows you to both sort and organize.

Windows: Option + Shift + O
Mac: option + shift ++ o




Control + Space to open snippets
This makes it easy to do things like type `main` and get if __name__ == 'main'...

## Terminal

The built-in terminal is a wonderful idea. You can pull it up with control + '`', on either mac or windows. You can also pull it up from dragging up from the bottom of the screen.

## Jupyter

Shift enter to run through python interactive console


## Don't write .pyc files

PYTHONDONTWRITEBYTECODE=1

## Code Completion

Control + Space to pull it up manually

## Shortcuts

"cwd": "${workspaceFolder}",

or

"cwd": "${fileDirname}"


## launch.json ##
justmycode is useful
- defaults to true
- restricts debugging to only the user-written code

## .env files ##
Go at top of directory. Can add environment variables, python path, etc.

- don't use quotes in variables names here
