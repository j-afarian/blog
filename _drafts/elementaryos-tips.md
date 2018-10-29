---
layout: post
comments: true
title:  "Things to do after installing ElementaryOS"
categories: Linux
tags: [Linux, ElementaryOS, Operating System, tweaks, to-do]
---
If you've made the decision to install ElementaryOS Juno (5.0), here are a few things you can do to make sure you're getting the most out of your new operating system.

### 1. Enable PPA
By default, you can't add PPA's in ElementaryOS. Enabling them is quick and easy:
```
sudo apt-get install software-properties-common
```

### 2. Install Elementary Tweaks
Elementary Tweaks will enable you to easily update icons and themes, as well as a few other nifty settings.
```
sudo add-apt-repository ppa:philip.scott/elementary-tweaks
sudo apt-get update
sudo apt-get install elementary-tweaks
```

### 3. Install Gdebi
Gdebi allows you to easily click-to-install .deb files.
```
sudo apt-get install gdebi
```
