Contributing to DBGp XDebug
===========================
DBGp XDebug is an open source project. Anyone can use the code, but more importantly, anyone can contribute. This is a
 group effort and we value your input. Please consider making a contribution to help improve the DBGp XDebug. This
 guide covers:  

* How to file a ticket when you discover a bug  
* How to contribute fixes and improvements to the core  
* Information on how to improve the documentation  

### Notification via Ticket

You can also search existing bug reports/issues and file a new one if you do not find an issue relevant to your
 proposed change. See Filing an Issue for more details.  

## Filing an Issue

If you would like to file a bug report, please create an issue in our Github Issues Tracker. You should do a basic
 search of the issues database before creating a new issue to ensure that you are not creating a duplicate issue.  

### Providing a Patch

If you are filing and issue and supplying a patch at the same time, please file a Pull Request instead. The pull
 request will also create an issue at the same time but its superior to just creating an issue because the code and
 issue can be linked.  

If the ticket already exists, however, and you want to supply a patch after the fact,
 you can simply reference the issue number in your commit message. For example, if your commit fixed issue #123 you
 could use the following commit message:  

    Fixed a problem with breakpoints

    [Fixes #123]

Github will automatically detect this commit message when you push it and link the issue. Please see the detailed
 Github Issues blog post for more details.  

### Feature Requests

We’re interested in hearing your ideas for new features. A feature request is any idea you have to improve the software experience that
 is not strictly related to a bug or error of omission.  

Feature requests that are accompanied by source code are always welcome. In this case you should read the next
 section on Creating a Pull Request.  

## Creating a Pull Request

If you are going to contribute code to the DBGp XDebug project, the best mechanism for doing this is to create a pull
 request in Github. If you’re unfamiliar with the general concept of pull requests you may want to read more on pull
 requests in Github.  

If your code is associated with an existing issue then you can provide a patch instead of creating a pull request.

### Creating a Fork

The official DBGp XDebug source code is maintained in Github under the AlexParamonov/dbgp_xdebug  

You simply need to “fork” the project and then start hacking.  

See the Github guide on creating forks for more details.  

### Topic Branches

Git branches are “cheap.” Creating branches in Git is incredibly easy and its an ideal way to isolate a specific set
 of changes. You may be fixing several things at one time but by keeping your changes isolated it will help us to
 find and apply only the changes we’re interested in. You should create a clean branch based on the latest
 dbgp_xdebug/master when doing this. It is important you follow these steps exactly,
 it will prevent you from accidentally including unrelated changes from your local repository into the branch.  

For example, if we were submitting a patch to fix an issue with the breakpoints you could create
 a branch as follows:  

    $ git remote add upstream git://github.com/AlexParamonov/dbgp_xdebug.git
    $ git fetch upstream
    $ git checkout -b fix-breakpoints --track upstream/master

The fetch command will grab all of the latest commits from the DBGp XDebug master branch. Don’t worry,
 it doesn’t alter your working repository in a harmful way. The track part of the command will tell git that this
 branch should track with the remote version of the upstream master. This is another way of saying that the branch
 should be based on a clean copy of the latest official source code (without any of your unrelated local changes.)  

You can then do work locally on this topic branch and push it up to your Github fork when you are done. So in our
 previous example we do something like:  

    $ git push origin fix-breakpoints

Of course if you want the fix for yourself to use in your own local code you should probably merge it down to your
 own personal master branch that you’re using for development  

    $ git checkout master
    $ git merge fix-breakpoints

You should probably also clean up after yourself a little. The branch has been pushed to Github and you’ve merged it
  locally so you don’t really need a local copy of the branch laying around.

    $ git branch -D fix-breakpoints

### Creating the Pull Request

Once your code is ready to go and you have pushed your topic branch to Github then you are ready to create the pull
 request and notify the DBGp XDebug team that your contribution is ready. You do this by browsing your project in
 Github and changing to the topic branch you just pushed. Once you are on the topic branch simply create a pull
 request by pressing the “Pull Request” button.  

The Github guide on pull requests describes this in more detail with screenshots if you’re still confused on this
 part.  

## Contributing to the Documentation
Improvements to the documentation is encouraged.
