---
title: 'Behind Enemy Lines: Using git as a frontend to svn'
author: Jeremy
layout: post
permalink: /2012/09/behind-enemy-lines-using-git-as-a-frontend-to-svn/
dsq_thread_id:
  - 834779405
categories:
  - code
---
Sometimes a developer may find themselves forced to use tools that may not be&#8230; preferable. This is the situation I&#8217;ve found myself in working at a large company where subversion is the source control management software of choice. While I should fight the good fight and try to change policy to use git instead, I have to get work done in the meantime, so I&#8217;m using <a onclick="javascript:pageTracker._trackPageview('/outgoing/www.kernel.org/pub/software/scm/git/docs/git-svn.html');"  href="http://www.kernel.org/pub/software/scm/git/docs/git-svn.html">git svn</a>.

Over the past year, after a rocky start, I&#8217;ve fallen into a groove with how I&#8217;ve integrated git svn into my workflow. Since it was pretty confusing in the beginning, I figured I should finally post my notes to help anyone else facing the same situation. This guide doesn&#8217;t dive deep into the intricacies of branching and merging &#8211; it focuses on pushing commits to svn, pulling other peoples&#8217; changes from svn, and dealing with conflicts along the way.

## General workflow {#generalworkflow}

Pushing and pulling changes to/from svn requires a clean repo, so the first thing to do is stash any uncommitted changes.

### Pull the latest revision {#pullthelatestrevision}

    git stash
    git svn rebase
        (resolve any conflicts caused by local commits)
    git stash pop
        (resolve any conflicts caused by stashed content)
    

### Push your commits to svn {#pushyourcommitstosvn}

    git stash
    git svn dcommit
    git stash pop
        (resolve any conflicts)
    

### A note about dcommit {#anoteaboutdcommit}

The dcommit command stands for &#8220;duplicate commit&#8221;. While it sounds straightforward, it&#8217;s helpful to know what the command actually does: once it duplicates your commits to svn, it deletes them from your local repository, then rebases to pull those same commits back from svn.

    git svn dcommit
        1. duplicate commits to svn
        2. delete local copy of those commits
        3. rebase to pull those commits from svn
    

## Resolving Conflicts {#resolvingconflicts}

There are two common places where you&#8217;ll experience conflicts while using git svn: after rebase and after popping the stash. It helps to use a different strategy depending on which command caused the conflict.

### Resolving conflicts during rebase {#resolvingconflictsduringrebase}

    git svn rebase
        M   config/environments/development.rb
        First, rewinding head to replay your work on top of it...
        Auto-merging config/environments/development.rb
        CONFLICT (content): Merge conflict in config/environments/development.rb
    

You may notice that we&#8217;re no longer on any branch:

    git branch -a
    * (no branch)
      master
      remotes/trunk
    

That&#8217;s okay though, just resolve the conflicts as usual:

    git mergetool
        Merging:
        config/environments/development.rb
    

Once you&#8217;re finished resolving the conflicts, continue the rebase:

    git rebase --continue
    

And we&#8217;re back on the master branch:

    git branch -a
    * master
      remotes/trunk
    

However, running `git status` shows that there&#8217;s nothing staged even though we changed the files during conflict resolution. Don&#8217;t worry, the changes made during confict resolution were combined with the commit that caused the confict during the `git rebase --continue`.

### Resolving conflicts while popping the stash {#resolvingconflictswhilepoppingthestash}

Here&#8217;s what the stash stack looks like before we attempt to pop:

    git stash list
    stash@{0}: WIP on master: d900c3c Fixing bug #502.
    

And here&#8217;s the conflict when we go to pop the latest stash:

    git stash pop
        Auto-merging config/environments/development.rb
        CONFLICT (content): Merge conflict in config/environments/development.rb
    

Just like usual, resolve the conflicts:

    git mergetool
        Merging:
        config/environments/development.rb
    

Unlike conflicts shown above when running `git svn rebase`, you have to commit the changes made while resolving the conflicts.

    git commit -a -m "Resolving Conflicts"
    

We&#8217;re not quite done yet. Although we&#8217;ve successfully merged the stash, it&#8217;s actually still there:

    git stash list
        stash@{0}: WIP on master: d900c3c Fixing bug #502.
    

The stash remains because git keeps it when conflicts are found so no work gets lost.

It&#8217;s a good idea to drop this immediately after resolving the conflicts. If you don&#8217;t, you might come across it later and wonder if you actually merged the stash or not, which will certainly result in more conflicts if you did indeed merge it previously.

    git stash drop
        Dropped refs/stash@{0} (0a7aeafd302d4b2bfa48fbbf7b9ac67544fc5d2d)
    

If you want to ensure you&#8217;re not dropping an important stash, you can always run a diff against the stash:

    git stash show -u
    

And finally, push the conflict resolutions to svn:

    git svn dcommit
    

## Conclusion {#conclusion}

I hope this helps people that find themselves in a similar situation to my own. Although I&#8217;ve found a workflow that fits my day to day activities, I&#8217;m no expert. If there are any errors or better ways of doing things please leave a comment and let me know!