---
title: GCode Viewer
author: Jeremy
layout: post
permalink: /2012/10/gcode-viewer/
dsq_thread_id:
  - 158 http://jherrman.com/?p=158
categories:
  - 3D
  - code
tags:
  - 3d printing
---
For the past couple of months, I&#8217;ve been working on my first WebGL project: enhancements to <a onclick="javascript:pageTracker._trackPageview('/outgoing/joewalnes.com/2012/04/01/a-3d-webgl-gcode-viewer-for-understanding-3d-printers/');"  href="http://joewalnes.com/2012/04/01/a-3d-webgl-gcode-viewer-for-understanding-3d-printers/">Joe Walnes</a>&#8216; excellent online <a onclick="javascript:pageTracker._trackPageview('/outgoing/gcode.joewalnes.com');"  href="http://gcode.joewalnes.com">GCode Viewer</a>. I&#8217;ve added some neat features like individual GCode coloring, animation, and the ability to scrub through GCode.

Give it a try here: <a onclick="javascript:pageTracker._trackPageview('/outgoing/jherrm.github.com/gcode-viewer/');"  href="http://jherrm.github.com/gcode-viewer/">http://jherrm.github.com/gcode-viewer</a>. Just drag &#038; drop your GCode on the window. Right now it works best with GCode made for additive manufacturing.  
<a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/jherrm/gcode-viewer');"  href="https://github.com/jherrm/gcode-viewer"><img src="http://jherrman.com/wp-content/uploads/2012/10/Screen-Shot-2012-10-19-at-2.12.48-AM-1024x543.png" alt="" title="GCode Viewer Screenshot" width="640" height="339" class="aligncenter size-large wp-image-159" /></a>

I&#8217;m looking forward to adding some more features like custom colors, better controls, and more GCode support. I&#8217;ve made some fairly large changes to the underlying architecture which should make adding and rendering more GCodes pretty simple. Included in the source code is an unfinished <a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/jherrm/gcode-viewer/blob/master/web/gcode_interpreter.js');"  href="https://github.com/jherrm/gcode-viewer/blob/master/web/gcode_interpreter.js">javascript port</a> of <a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/grbl/grbl/blob/edge/gcode.c');"  href="https://github.com/grbl/grbl/blob/edge/gcode.c">grbl&#8217;s GCode interpreter</a>, hopefully paving the way for full simulation someday.

Get the source code at <a onclick="javascript:pageTracker._trackPageview('/outgoing/github.com/jherrm/gcode-viewer');"  href="https://github.com/jherrm/gcode-viewer">https://github.com/jherrm/gcode-viewer</a>.
