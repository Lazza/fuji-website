---
title: Running in a live macOS environment
---

1. Connect the destination drive to the target Mac computer
2. Either connect your **Fuji Cartridge** drive or open a copy of the Fuji DMG
3. Click on *Full Disk Access Settings.url*
4. If the window has a "lock" icon, unlock it
5. Drag the *Fuji.app* file on the list of authorized apps **and ensure the
   toggle is enabled**
6. Now you can run *Fuji.app*
7. When prompted, insert the password for the administrator user

<figure class="icon-figure" markdown="span">
![Icon of the app with Mount Fuji at dawn with a juicy apple as sun](../img/Fuji-icon.png)
<figcaption>Icon of the Fuji app</figcaption>
</figure>

## Important notes

1. Before starting the acquisition, you must specify on what drive(s) you want
   to store temporary files and the final DMG file. Both values are
   `/Volumes/Fuji` by default and the *image name* parameter will be used to make
   a new directory inside those locations.

2. You must not save the disk images on the same drive you are acquiring!

3. If you use the Rsync mode, it is recommended to **close all other
   applications before proceeding, especially Apple Mail,** otherwise some data
   might not be collected.

## Video tutorial

The following video shows the acquisition process in a live macOS environment:

<iframe width="560" height="315" src="https://www.youtube.com/embed/9ZkLdFodhzM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
