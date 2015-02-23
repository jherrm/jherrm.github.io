---
title: The Most Useless iPhone Case Ever
author: Jeremy
layout: post
permalink: /2012/03/the-most-useless-iphone-case-ever/
dsq_thread_id:
  - 617144020
categories:
  - random
---
When I heard about the <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.makerbot.com/blog/2012/02/27/wanna-win-a-replicator-makerbot-evd-present-the-absurd-iphone-accessory-contest/');"  href="http://www.makerbot.com/blog/2012/02/27/wanna-win-a-replicator-makerbot-evd-present-the-absurd-iphone-accessory-contest/" title="Absurd iPhone Accessory Contest" target="_blank">Absurd iPhone Accessory Contest</a>, I knew I *had* to participate. My first entry, a <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.thingiverse.com/thing:18690');"  href="http://www.thingiverse.com/thing:18690" title="Voltron iPad" target="_blank">Voltron iPad</a> was thrown together pretty quickly and would be near impossible to print out on my makerbot cupcake&#8217;s modest build platform. I really wanted to submit an entry that I could actually print and that was a bit more interactive than a simple case. That was about 2 weeks ago, and I&#8217;ve been working on something ever since.

<a onclick="javascript:pageTracker._trackPageview('/outgoing/www.flickr.com/photos/jherrm/6852149960/');"  href="http://www.flickr.com/photos/jherrm/6852149960/" title="IMG_5828 by jherrm, on Flickr"><img src="http://farm8.staticflickr.com/7277/6852149960_5db8a0815d.jpg" width="500" height="375" alt="IMG_5828" /></a>

I&#8217;ve always wanted to build <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.instructables.com/id/The-Most-Useless-Machine/?ALLSTEPS');"  href="http://www.instructables.com/id/The-Most-Useless-Machine/?ALLSTEPS" title="The Most Useless Machine Ever" target="_blank">The Most Useless Machine Ever</a>, so I thought &#8211; why not combine it with an iPhone to create <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.thingiverse.com/thing:19503');"  href="http://www.thingiverse.com/thing:19503" target="_blank">The Most Useless iPhone Case Ever</a>? It turned out to be a pretty challenging project.

The typical &#8220;Most Useless Machine Ever&#8221; is many times the size of an iPhone, so the first thing I set out to do is find the smallest parts I could. The bill of materials for this project looks like this:

  * Battery case
  * Motor/Servo
  * Gearbox
  * DPDT Toggle Switch
  * SPDT Microswitch

<a onclick="javascript:pageTracker._trackPageview('/outgoing/www.flickr.com/photos/jherrm/6998273407/');"  href="http://www.flickr.com/photos/jherrm/6998273407/" title="IMG_5819 by jherrm, on Flickr"><img src="http://farm7.staticflickr.com/6117/6998273407_4d74c0313d.jpg" width="500" height="375" alt="IMG_5819" /></a>

Luckily I had all of these parts lying around the house in some form or another. The parts that were a real challenge to find were a motor and gearbox strong enough to flip the toggle switch but small enough to fit in a fairly large iPhone case. I remembered I had an old Creative Webcam in the junk pile that had pan/tilt functionality. After taking it apart I had two small gearboxes with the stepper motors the size of a peanut. It took a few hours to track down the information about them but eventually I was able to drive them via an arduino. Unfortunately, after all that work the steppers simply weren&#8217;t strong enough to flip either of the switches, so I had to find another solution. Of course, with an electronics hoarder like myself there&#8217;s always more broken electronics to look through, and I found just the right motor in a broken Canon Elph camera. A big benefit is the Canon&#8217;s lens motor is DC, so I don&#8217;t need a microcontroller to drive it. In fact, with a simple DC motor all of the functionality of the useless machine can be wired with <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.instructables.com/id/The-Most-Useless-Machine/step5/Wiring-Diagram/');"  href="http://www.instructables.com/id/The-Most-Useless-Machine/step5/Wiring-Diagram/">no chips at all</a>.

The real trouble came when even that motor didn&#8217;t seem to be strong enough to push the toggle switch over. I spent an embarrassingly long time tracking down easier to flip toggle switches before I realized that I needed More Power (insert Tim the Toolman Taylor grunt here). I had been using two AA batteries which just didn&#8217;t give the motor enough torque to flip the switch. I changed over to a 4xAA case and we were in business! Unfortunately everything has its price &#8211; another 10mm to the thickness of the case with the new battery holder.

After getting all of the parts, I set out to design the case via pencil and paper, then in the programmer&#8217;s 3D modeler of choice: OpenSCAD.

<a onclick="javascript:pageTracker._trackPageview('/outgoing/www.flickr.com/photos/jherrm/6997161555/');"  href="http://www.flickr.com/photos/jherrm/6997161555/" title="Useless iPhone Case by jherrm, on Flickr"><img src="http://farm8.staticflickr.com/7267/6997161555_f10977aca3_m.jpg" width="240" height="216" alt="Useless iPhone Case" /></a>

<a onclick="javascript:pageTracker._trackPageview('/outgoing/www.flickr.com/photos/jherrm/6997161843/');"  href="http://www.flickr.com/photos/jherrm/6997161843/" title="Useless iPhone Case Internals by jherrm, on Flickr"><img src="http://farm8.staticflickr.com/7218/6997161843_6692210545_m.jpg" width="240" height="238" alt="Useless iPhone Case Internals" /></a>

Aside from the electrical components, everything else is 3D printed, except for the toggle switch handle extension (my printer just couldn&#8217;t deliver anything small enough that would work well). I found the inside plastic piece from a mechanical pencil worked well, so I just used that.

<a onclick="javascript:pageTracker._trackPageview('/outgoing/www.flickr.com/photos/jherrm/6852151582/');"  href="http://www.flickr.com/photos/jherrm/6852151582/" title="IMG_5835 by jherrm, on Flickr"><img src="http://farm8.staticflickr.com/7192/6852151582_1d99160550.jpg" width="500" height="375" alt="IMG_5835" /></a>

It took a *lot* of revisions to get it right.

<a onclick="javascript:pageTracker._trackPageview('/outgoing/www.flickr.com/photos/jherrm/6997763321/');"  href="http://www.flickr.com/photos/jherrm/6997763321/" title="Useless iPhone Case Prototypes by jherrm, on Flickr"><img src="http://farm8.staticflickr.com/7132/6997763321_328fafc767_m.jpg" width="240" height="180" alt="Useless iPhone Case Prototypes" /></a>

Anyways, I could go on for a long time about this case, but the details are pretty boring. It&#8217;s all done now just in time for the deadline of the contest. Everything would have went a lot quicker if I had a better 3D printer (hint hint to the judges&#8230;), although I do love my cupcake.

Check it out on thingiverse: <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.thingiverse.com/thing:19503');"  href="http://www.thingiverse.com/thing:19503">The Most Useless iPhone Case Ever</a>