---
title: "The making of the NumPy Roadmap"
date: 2018-10-20
categories:
- Python
tags:
- NumPy
- roadmap
---

NumPy now has a [roadmap](https://www.numpy.org/neps/index.html#roadmap) - long overdue and a major step forward for the project.  We're not done yet (see [my previous post](https://rgommers.github.io/2018/10/2018-numfocus-summit---a-summary/) on this topic) and updating the technical roadmap with new ideas and priorities should happen regularly.  Despite everything having been done in the open, via minutes of in-person meetings and shared roadmap drafts on the numpy-discussion mailing list, it turns out that it's not completely clear to the community and even some maintainers how we got to this point.  So now seems like a good time for a summary.

## Act 1: NumPy sprint at BIDS

During 24-25 May 2018 a number of people - Stéfan van der Walt, Charles Harris, Stephan Hoyer, Matti Picus, Jarrod Millman, Jaime Fernandez del Rio, Nathaniel J. Smith, and Matthew Rocklin - came together at [BIDS](https://bids.berkeley.edu/) in Berkeley for a NumPy sprint.  They had a productive brainstorm, which resulted in a rough draft of a roadmap posted to the mailing list.  The mailing list thread, [A roadmap for NumPy - longer term planning](https://mail.python.org/pipermail/numpy-discussion/2018-June/thread.html#78103), produced more suggestions and after incorporating those a [first pull request](https://github.com/numpy/numpy/pull/11446) was made.

## Act 2: BoF and sprint at SciPy'18

In order to collect input from as many people in the community as possible, a BoF ([birds of a feather](https://en.wikipedia.org/wiki/Birds_of_a_feather_(computing) session) was held on 12 July 2018 during the SciPy 2018 conference in Austin.  Stephan Hoyer presented an overview of recent NEPs, and Matti Picus presented the first roadmap draft and led a discussion with (I estimate) 30-40 people in which a number of new ideas were added.  Other maintainers present included Charles Harris, Tyler Reddy, Ralf Gommers and Stéfan van der Walt; many other participants were developers of libraries that depend on NumPy.

At this point we had a fairly complete list of roadmap items, however the document itself was still more a brainstorm dump than a roadmap document.  So during the NumPy sprint after the conference on 14 July 2018 Ralf Gommers and Stephan Hoyer sat together to reshape and clean up these ideas.  That resulted in [roadmap draft v2](https://github.com/numpy/numpy/wiki/NumPy-roadmap-v2) - not yet fully polished, but getting closer to something ready for acceptance.

## Act 3: NumPy sprint at BIDS

In-person meetings seem to be critical to moving a complex and important document like a project roadmap forward.  So the next draft was produced during a second NumPy sprint at Berkeley during 23-27 July 2018.  Present were Stéfan van der Walt, Matti Picus, Tyler Reddy and Ralf Gommers.  We polished the document, worked out the [Scope of NumPy](https://www.numpy.org/neps/scope.html) section in more detail, and integrated the roadmap in the html docs.  During the sprint a [pull request](https://github.com/numpy/numpy/pull/11611) was sent, and [posted](https://mail.python.org/pipermail/numpy-discussion/2018-July/thread.html#78458) again to the mailing list.  Everyone seemed happy, and after addressing the final few review comments the roadmap was merged on 2 August 2018.

*Final thought: NumPy development is accelerating at the moment, and in-person meetings and having the people and funding at BIDS to organize sprints has been a huge help. See https://github.com/BIDS-numpy/docs for an overview of what has been organized in the last year.*
