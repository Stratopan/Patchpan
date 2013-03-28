Patchpan
========

Where old code gets a new life

What Is This?
========

There are tens of thousands of distributions on CPAN.  Unfortunately, 
some of them are broken in some way, which makes them difficult for
tools like Pinto to index them.  Usually, it is just a matter of
adding or fixing the META files in the distribution.  But the CPAN
infrastructure doesn't really provide a way to re-release an old
distribution with different META.

So the idea here is to create a CPAN-like repository that contains
patched versions of those distributions.  Then, you can point Pinto
at this repository and pull a variant of these old distributions 
that have accurate META.

In effect, this is a crowd-sourced clean up of CPAN.  If someone finds
a distribution that is broken, then can patch it and put it here.
Then everyone using Pinto (or just cpan or cpanm) can take advantage
of these patched distributions.

How Do I Make a Patch?
========

First, obtain the original tarball from either CPAN or BackPAN.  Unpack
it, make your changes, run tests (if appropriate) and then repack it.
You should pack it in the same format as the original (e.g. tar.gz or
zip).

In general, you should limit the scope of your changes to the META files.
Do not add functionality, fix bugs, or change version numbers.  On
occasion, you may need to remove, relocate, or modify a file so that it
does (or does not) get indexed properly.  But that should be rare.

I've Pathced A Distribution.  What Now?
========

Fork this repository and place the archive format into the repository.
The layout matches a typical CPAN repsitory.  So if the original 
distribution was written by "DCONWAY" and named "Foo-Bar-1.20.tar.gz" 
then you would place your patched distribution in the repository at this 
path:

```
authors/id/D/DC/DCONWAY/Foo-Bar-PATCHED-1.20.tar.gz
```

Finally, make a pull request to have your patched distribution merged
into the PatchPAN.  And that's it!

How Do I (or others) Get These Patched Dists?
========

For now, you can just clone this repository.  But at some point, I plan
to setup a public Pinto repository where folks can fetch the distributions
using Pinto or cpanm.

Who Has The Authority To Do This?
========

This is all happening *outside* of the official CPAN ecosystem, so these
distributions do not conflict with the permission system that PAUSE uses.
If you are able to contact the author of the original distribution, it
is probably wise to contact them and tell them what you are doing.  They
might give you some suggestions on how to best "fix" the distribution.
However, you don't necessarily need their blessing, so long as the code
has an appropriate license (which I believe all CPAN dists must).

Where Can I Learn More About This?
=========

Send questions, comments, and concerns to jeff@stratopan.com
