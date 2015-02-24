---
title: Introducing ScanBooth
author: Jeremy
layout: post
permalink: /2012/10/introducing-scanbooth/
dsq_thread_id:
  - 144 http://jherrman.com/?p=144
categories:
  - 3D
  - code
tags:
  - 3d printing
  - 3D scanning
  - kinect
  - Pittsburgh
---
<div id="attachment_146" style="width: 650px" class="wp-caption aligncenter">
  <a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/10/B01071.jpeg');"  href="http://jherrman.com/wp-content/uploads/2012/10/B01071.jpeg"><img src="http://jherrman.com/wp-content/uploads/2012/10/B01071-1024x682.jpeg" alt="ScanBooth at Pittsburgh Mini Maker Faire 2012" title="ScanBooth at Pittsburgh Mini Maker Faire 2012" width="640" height="426" class="size-large wp-image-146" /></a>

  <p class="wp-caption-text">
    Kids getting 3D scanned at the Pittsburgh Mini Maker Faire 2012. © Larry Rippel
  </p>
</div>

At the <a onclick="javascript:pageTracker._trackPageview('/outgoing/pghmakerfaire.com');"  href="http://pghmakerfaire.com">2012 Pittsburgh Mini Maker Faire</a>, I ran a booth where people could get 3D scanned and take home a small printout of themselves. After an intense 7 hours, we scanned over 90 people and printed out over 40 of them. Going from raw 3D scan to a printable miniature figurine requires a surprising number of steps. Raw 3D scans have holes, extra geometry and artifacts that all need to be dealt with before sending to the printer. In fact, when I first started scanning people back in March, it took me over an hour to manually clean up a scan so that it was able to be printed out. In order to scan and print so many people in such a short time span, I had to automate the process as much as possible. Using a collection of scripts I was able to get the turnaround time down from over an hour to about 8 minutes. To help others with this problem, I&#8217;m releasing <a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/jherrm/scanbooth');"  href="https://github.com/jherrm/scanbooth">ScanBooth</a>.

<a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/jherrm/scanbooth');"  href="https://github.com/jherrm/scanbooth">ScanBooth</a> is a collection of software for running a 3D photo booth. It includes tools for automating 3D scan capture, cleanup, printing and sharing.

Here&#8217;s what ScanBooth has to offer:

  * A rails webapp
      * Allows users to enter their contact information when they get scanned.
      * Stores status of user prints, uploads and emails.
  * Delayed job framework
      * Upload scans to <a onclick="javascript:pageTracker._trackPageview('/outgoing/sketchfab.com');"  href="http://sketchfab.com">sketchfab</a>.
      * Upload scans to an FTP server.
      * Email users links to their scans for viewing/downloading.
  * Scan workflow automation
      * Auto launch ReconstructMe and start scan
      * Automated scan cleanup with <a onclick="javascript:pageTracker._trackPageview('/outgoing/sourceforge.net/projects/meshlab');"  href="http://sourceforge.net/projects/meshlab">meshlab</a>

We had a fantastic time showing people the power of 3D scanning and printing at Pittsburgh Mini Maker Faire. I hope ScanBooth helps others do the same. Please check out the code on <a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/jherrm/scanbooth');"  href="https://github.com/jherrm/scanbooth">github</a> and let me know what you think!

<div id="attachment_148" style="width: 650px" class="wp-caption aligncenter">
  <a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/10/B0147.jpeg');"  href="http://jherrman.com/wp-content/uploads/2012/10/B0147.jpeg"><img src="http://jherrman.com/wp-content/uploads/2012/10/B0147-1024x682.jpeg" alt="" title="Carlos Armengol and son." width="640" height="426" class="size-large wp-image-148" /></a>

  <p class="wp-caption-text">
    Carlos Armengol and his son check out their souvenir from ScanBooth at Pittsburgh Mini Maker Faire 2012. © Larry Rippel
  </p>
</div>

<p><iframe frameborder="0" height="480" width="854" allowfullscreen="" webkitallowfullscreen="true" mozallowfullscreen="true" src="http://skfb.ly/k4j32ed0a?autostart=0&amp;transparent=0&amp;autospin=0&amp;controls=1&amp;watermark=1"></iframe></p>
