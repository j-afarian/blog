---
layout: post
comments: true
title:  "Installing RuneScape on Linux"
categories: Linux
tags: [Linux, Games, RuneScape, Tutorial, Guide, Install]
---
<div class="box alt"><div class="row uniform">
<div class="12u$"><span class="image fit"><img src="/images/games/AngryRS.png" alt="Angry Runescape" /></span></div>
</div></div>
Installing RuneScape on Linux has proven difficult every time I've had to do it, there are multiple hoops you need to jump through to get it working.

I recently re-installed my operating system, so decided to document the troubleshooting steps I took to get the game up and running for future reference.

### The Official Instructions
According to the website ([https://www.runescape.com/download](https://www.runescape.com/download)), downloading and installing the client should be as easy as running the following in terminal:
```
sudo -s -- << EOF
wget -O - https://content.runescape.com/downloads/ubuntu/runescape.gpg.key | apt-key add -
mkdir -p /etc/apt/sources.list.d
echo "deb https://content.runescape.com/downloads/ubuntu trusty non-free" > /etc/apt/sources.list.d/runescape.list
apt-get update
apt-get install -y runescape-launcher
EOF
```

You can try it, but it's probably not going to work - so let's get right into the troubleshooting steps!

**E: The repository 'https://content.runescape.com/downloads/ubuntu trusty InRelease' is not signed.**  
Replace vim with your code editor of choice, and run the following:
```
sudo vim /etc/apt/sources.list.d/runescape.list
```
change
```
deb https://content.runescape.com/downloads/ubuntu trusty non-free
```
to
```
deb [trusted=yes] https://content.runescape.com/downloads/ubuntu trusty non-free
```

**runescape-launcher : Depends: libglew1.10 (>= 1.10.0-3) but it is not installable**  
```
sudo wget http://launchpadlibrarian.net/161405671/libglew1.10_1.10.0-3_amd64.deb
```
```
sudo dpkg -i libglew1.10_1.10.0-3_amd64.deb
```

**E: There were unauthenticated packages and -y was used without --allow-unauthenticated**  
```
sudo apt-get install -y --allow-unauthenticated runescape-launcher
```

**Game installs, but won't launch (no error, just doesn't appear)**  
```
sudo wget http://launchpadlibrarian.net/233197129/libpng12-0_1.2.54-1ubuntu1_amd64.deb
```
```
sudo dpkg -i libpng12-0_1.2.54-1ubuntu1_amd64.deb
```
```
sudo apt-get install libcurl3
```

**Crackling game sound**  
Replace vim with your code editor of choice.
```
sudo vim /usr/share/applications/runescape-launcher.desktop
```
change
```
Exec=/usr/bin/runescape-launcher %u
```
to
```
Exec=env PULSE_LATENCY_MSEC=100 runescape-launcher %u %F
```

Hopefully these steps have been helpful :) Happy gaming!

<div class="box alt"><div class="row uniform">
<div class="12u$"><span class="image fit"><img src="/images/games/YayRS.png" alt="Angry Runescape" /></span></div>
</div></div>
