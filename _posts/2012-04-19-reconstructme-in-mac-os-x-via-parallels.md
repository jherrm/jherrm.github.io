---
title: ReconstructMe in Mac OS X via Parallels
author: Jeremy
layout: post
permalink: /2012/04/reconstructme-in-mac-os-x-via-parallels/
dsq_thread_id:
  - 110 http://jherrman.com/?p=110
categories:
  - 3D
---
<a onclick="javascript:pageTracker._trackPageview('/outgoing/reconstructme.net');"  href="http://reconstructme.net">ReconstructMe</a> is a great tool for 3D scanning with the kinect and other depth cameras. Unfortunately it&#8217;s Windows only, and due to shoddy device handling in virtualization programs like VMware Fusion and VirtualBox the kinect isn&#8217;t recognized by Windows.

Luckily, thanks to <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.parallels.com/');"  href="http://www.parallels.com/">Parallels</a> all hope is not lost. Here&#8217;s how I was able to 3D scan with ReconstructMe in a Windows VM:

This guide assumes you have a running Windows 7 instance inside a copy of Parallels 7.

Let&#8217;s start with the <a onclick="javascript:pageTracker._trackPageview('/outgoing/reconstructme.net/installation/');"  href="http://reconstructme.net/installation/">installation instructions</a> from ReconstructMe:

**Display and CPU Drivers**

****If you try to install display drivers in a virtual machine you&#8217;ll likely get an error like this:

<div id="attachment_113" style="width: 622px" class="wp-caption aligncenter">
  <a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/04/NVIDIA-nogo1.png');"  href="http://jherrman.com/wp-content/uploads/2012/04/NVIDIA-nogo1.png"><img class="size-full wp-image-113" title="NVIDIA No Go" src="http://jherrman.com/wp-content/uploads/2012/04/NVIDIA-nogo1.png" alt="" width="612" height="456" /></a>

  <p class="wp-caption-text">
    Native display drivers don't typically work inside virtual machines.
  </p>
</div>

The real reason we need these drivers is for OpenCL support, which ReconstructMe relies on. After getting that error message, I just skipped this section and continued with the installation. Because I didn&#8217;t have OpenCL support I ended up getting this message on the first run of ReconstructMe:

<p style="text-align: center;">
  <a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/04/OpenCL-nogo.png');"  href="http://jherrman.com/wp-content/uploads/2012/04/OpenCL-nogo.png"><img class="aligncenter size-full wp-image-112" title="OpenCL not found" src="http://jherrman.com/wp-content/uploads/2012/04/OpenCL-nogo.png" alt="The program can't start because OpenCL.dll is missing from your computer. Try reinstalling the program to fix this problem." width="468" height="178" /></a>
</p>

Luckily Intel provides an OpenCL CPU runtime for Windows that you can download <a onclick="javascript:pageTracker._trackPageview('/outgoing/software.intel.com/en-us/articles/vcsource-tools-opencl-sdk/');"  href="http://software.intel.com/en-us/articles/vcsource-tools-opencl-sdk/">here</a>.

<a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/04/OpenCL-CPU-Runtime.png');"  href="http://jherrman.com/wp-content/uploads/2012/04/OpenCL-CPU-Runtime.png"><img class="aligncenter size-full wp-image-114" title="OpenCL CPU Runtime" src="http://jherrman.com/wp-content/uploads/2012/04/OpenCL-CPU-Runtime.png" alt="" width="249" height="105" /></a>

Apart from installing the OpenCL runtime instead of the native graphics drivers, the rest of the <a onclick="javascript:pageTracker._trackPageview('/outgoing/reconstructme.net/installation/');"  href="http://reconstructme.net/installation/">installation instructions</a> are the same.  Just install the <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.microsoft.com/download/en/details.aspx?id=5555');"  href="http://www.microsoft.com/download/en/details.aspx?id=5555">C++ redistributables</a>, the Sensor Driver, and <a onclick="javascript:pageTracker._trackPageview('/outgoing/reconstructme.net/downloads');"  href="http://reconstructme.net/downloads">ReconstructMe</a>, then you&#8217;ll be all set to try it out.

The first time you plug your kinect into your mac while Parallels is running you&#8217;ll get three notifications that look like this:

<a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/04/USB-Camera.png');"  href="http://jherrman.com/wp-content/uploads/2012/04/USB-Camera.png"><img class="aligncenter size-full wp-image-115" title="USB Camera" src="http://jherrman.com/wp-content/uploads/2012/04/USB-Camera.png" alt="" width="484" height="590" /></a>

Be sure to select Windows for all three (Camera, Audio and Motor).

Now go ahead and give ReconstructMe a try!

A warning: Running anything in a virtual machine will never be as fast as running it natively, and this is especially true with ReconstructMe. Running it in realtime mode was VERY choppy and resulted in poor scans. I highly recommend running &#8220;ReconstructMe Record&#8221; which will simply record what the kinect sees at a decent framerate. Once you&#8217;ve captured what you want, open &#8220;ReconstructMe Replay&#8221; to go through your recording and build the scan. Here&#8217;s what came out of my first scan using record/replay:

<div id="attachment_116" style="width: 359px" class="wp-caption aligncenter">
  <a onclick="javascript:pageTracker._trackPageview('/downloads/wp-content/uploads/2012/04/MacPlus.png');"  href="http://jherrman.com/wp-content/uploads/2012/04/MacPlus.png"><img class="size-full wp-image-116" title="Mac Plus" src="http://jherrman.com/wp-content/uploads/2012/04/MacPlus.png" alt="" width="349" height="322" /></a>

  <p class="wp-caption-text">
    An appropriate first scan with ReconstructMe on a Mac
  </p>
</div>

Anyways, that&#8217;s it!  If you have any questions or comments, leave them here or hit me up on twitter!
