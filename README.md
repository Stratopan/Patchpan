Patchpan
========

Patchpan is a public repository of CPAN distributions that have been
cleaned up to meet modern CPAN specifications.

What Is This?
========

There are tens of thousands of distributions on CPAN.  Unfortunately, 
some of them have broken or missing metadata, which makes them difficult
for various systems like Pinto or MetaCPAN to correctly analyze them.
Usually, it is just a matter of adding or fixing the META files in the 
distribution.  But the CPAN  infrastructure doesn't really provide a way 
to re-release an old distribution with different META files.

So the idea here is to create a CPAN-like repository that contains
patched versions of those distributions.  Then you can point your tools
at this repository and pull a variant of those distributions with correct 
dependency information, version numbers, etc.

In effect, this is a crowd-sourced clean up of CPAN.  If someone finds
a distribution that is broken, they can patch it and put it here for
everyone else to utilize.

How Do I Make a Patch?
========

First, obtain the original tarball from either CPAN or BackPAN.  Unpack
it, make your changes, run tests (if appropriate) and then repack it.
Often times, all you have to do is regenerate the META files with a modern
version of ExtUtils::MakeMaker or Module::Build, or maybe inject a newer
version of Module::Install.

Other things you might do are add missing modules to the prereqs, or
fix version numbers that are invalid (2.4a is not kosher), or fix a
mispelled key in the META dictionary.  You might even explicitly list
all the provided modules in the META (this is what PAUSE prefers
nowadays).

In general, you should limit the scope of your changes to the META files.
Do not add functionality, fix bugs, or change version numbers.  On
occasion, you may need to remove, relocate, or modify a file so that it
does (or does not) get indexed properly.  But that should be very rare.

I've Pathced A Distribution.  What Now?
========

Fork this repository and place the archive into your fork.  The layout matches 
a typical CPAN repsitory.  So if the original distribution was written by 
"DCONWAY" and named "Foo-Bar-1.20.tar.gz" then you would place your patched 
distribution in the repository at this path:

```
authors/id/D/DC/DCONWAY/Foo-Bar-PATCHED-1.20.tar.gz
```

Finally, make a pull request to have your patched distribution merged into the 
PatchPAN.  And that's it!

How Do I (or others) Get These Patched Distributions?
========

For now, you can just clone this repository.  But at some point, I plan to setup 
a public Pinto repository where folks can fetch the distributions using Pinto 
or cpanm.

Who Has The Authority To Do This?
========

This is all happening *outside* of the official CPAN ecosystem, so these
distributions do not conflict with the namespace permission system that PAUSE 
uses.  If you are able to contact the author of the original distribution, it
is probably wise to let them know what you are doing.  They might give you some 
suggestions on how to best "fix" the distribution.  However, you don't necessarily 
need their blessing, so long as the code has an appropriate license (which I 
believe all CPAN dists must).

Where Can I Learn More About This?
=========

Send questions, comments, and concerns to jeff@stratopan.com
