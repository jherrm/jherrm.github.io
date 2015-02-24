---
title: How to tell if your LinkedIn password was part of the hack
author: Jeremy
layout: post
permalink: /2012/06/how-to-tell-if-your-linkedin-password-was-part-of-the-hack/
dsq_thread_id:
  - 109 http://jherrman.com/?p=109
categories:
  - random
---
Update: check out <a onclick="javascript:pageTracker._trackPageview('/outgoing/leakedin.org');"  href="http://leakedin.org">LeakedIn</a> for a much easier way to see if your password was part of the leak, as well as if it has already been cracked.

This assumes you&#8217;ve already downloaded the 118MB list of password SHA1&#8217;s. I&#8217;d link to the source I found but it has already been removed. (No, I&#8217;m not going to share mine &#8211; sorry).  This also assumes you&#8217;re on a Mac or linux box with OpenSSL installed.

Create a text file called `password_file.txt`.  Type your password into this file and save. Be sure not to include any spaces or new lines, just your password.

Open up a terminal and type the following, replacing &#8220;/path/to/&#8221; with the actual path to the password_file.txt file:

`openssl sha1 /path/to/password_file.txt`

You&#8217;ll get output simliar to this:

`SHA1(password_file.txt)= da39a3ee5e6b4b0d3255bfef95601890afd80709`

Copy that long string of text after the equals sign. Search for it in the list of SHA1&#8217;s, and if you find a match then your password was part of the hack. You should change your password for any accounts using that password immediately.

Also don&#8217;t forget to delete that file after generating the SHA1!
