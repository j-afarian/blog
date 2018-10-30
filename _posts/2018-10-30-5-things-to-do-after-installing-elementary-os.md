---
layout: post
comments: true
title:  "5 things to do after installing Elementary OS"
categories: Linux
tags: [Linux, Elementary OS, Operating System, tweaks, to-do]
---
<div class="box alt"><div class="row uniform">
<div class="12u$"><span class="image fit"><img src="/images/tech/eos.png" alt="Elementary OS Logo" /></span></div>
</div></div>
If you've made the decision to install Elementary OS Juno (5.0), here are a few things you can do to make sure you're getting the most out of your new operating system.

### 1. Enable PPA
By default, you can't add PPA's in Elementary OS. Enabling them is quick and easy:
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
Gdebi allows you to easily click-to-install .deb packages, resolving and installing its dependencies.
```
sudo apt-get install gdebi
```

### 4. Download other web browsers
By default, Elementary OS comes with Epiphany, but you may want something a little more familiar like Firefox or Chrome.
```
sudo apt-get install firefox
```
```
sudo apt-get install chromium-browser
```

### 5. Play games with Steam
There are plenty of Linux ported games available, but you can also opt-in to the Steam Play beta which allows you to play Windows games without an official port. Not all games will work, but it's much more convenient than setting up wine on your own as steam does all the leg work for you.
```
sudo apt-get install steam
```
