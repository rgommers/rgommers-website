---
title: "The cost of an open source contribution"
date: 2019-06-05
categories:
- Python
tags:
- open source
- maintainers
- sustainability
---

Open source is massively successful. Some say it's [eating the world](https://blog.iron.io/is-open-source-eating-the-world/), although to my ears that phrasing doesn't sound entirely like a good thing. Open source maintainers are always in need of help, and over the past years I've seen a lot of focus on ways open source projects can grow their communities and gain new contributors. Guidance on how to go about finding new contributors is easily found. E.g. GitHub publishes the excellent [opensource.guide](https://opensource.guide/), which covers everything from starting an open source project to best practices for maintainers and building welcoming communities.

NumPy and SciPy - the two projects I spend most time on - have between 100 and 150 unique contributors every release (i.e. over a 6 month period). Nevertheless those projects, like most popular community-driven projects, struggle to keep up with their issues, pull requests, and demand from users for new features and better documentation. The causes of that are less often discussed - although I do recommend every maintainer to read [Roads and Bridges - The Unseen Labor Behind Our Digital Infrastructure](https://www.fordfoundation.org/about/library/reports-and-studies/roads-and-bridges-the-unseen-labor-behind-our-digital-infrastructure/). 

This post is an attempt to summarize some of my thoughts on how to improve contribution and review patterns for projects in the PyData ecosystem (and perhaps beyond). Some of this content should probably make its way into contributor and developer guides.

> "Next to diversity, the high rate of maintainers having burnouts is one of the key issues in open source today." --
K Rain Leander, GitHub Satellite "Maintaining the maintainers" panel.

I couldn't agree more. The average maintainer has a full time job, works on open source as a labor of love (unpaid) in evenings, weekends or during the commute to work. Often what started as an interesting experiment or attempt to learn something new turned into something akin to a second job - with a pile of open issues, pull requests (PRs) and unanswered emails that you're feeling guilty about having ignored for too long already. 

Companies, which pay for labor, have to explicitly weigh the costs and benefits of starting a project or proposing a change. They typically have a  methodology for doing that, and there are libraries full of literature on topics like innovation management and technical business management. 
In contrast, in open source many people (even some experienced maintainers) believe that any change that's a technical improvement is inherently worthwhile. Just because a change is proposed by an unpaid volunteer, does not mean that there are no costs though!

Most maintainers review far more code than they write. If that statement sounds odd, I recommend reading Matt Rocklin's [blog post on roles in open source](https://matthewrocklin.com/blog//2019/05/18/maintainer). If you mostly write code, you're a (core) developer rather than a maintainer.

## Cost of a pull request

> A shocking amount of research looks at “contributors in, contributors out” as a means of measuring project health. This ignores the fact that total number of contributors does not correlate to whether a project survives. --
Nadia Eghbal, [Methodologies for measuring project health](https://nadiaeghbal.com/project-health)

Time of a maintainer is a scarce resource. So back to my original topic: costs of a contribution. For a pull request, these are the costs that need to be considered:

- *Each change has to be reviewed*. This is the single biggest cost.
- *Each change generates notifications*. Maintainers other than the ones actively reviewing also have to process these notifications. And no, this is not trivial or a matter of a few email filters. It takes me at least half an hour a day to keep track of GitHub and mailing list traffic. Matt Rocklin's [blog post](https://matthewrocklin.com/blog//2019/05/18/maintainer) talks about this too.
- *Each change causes code churn*. A change introduces a small risk of introducing new bugs, it adds to the history of the code which make it harder to debug other issues or use `git blame`, it puts a load on the CI system, and so on.

A recent conversation with a developer who was paid to work on a mostly volunteer-driven project made clear to me that these costs are not obvious. Paraphrasing:

- Developer: can someone please review this pull request?
- Me: I don't really want to, it doesn't seem like an important fix and it will take me time to wrap my head around that code.
- Developer: it's been ready for a while, so I just want to get it merged to get it off my list.
- Me: we should discuss priorities, I really don't want to review this.
- Developer: I get paid to work on this project, so I feel like I have to write code. My important tasks are waiting for discussion, so I worked on this instead.

Mixing funded and volunteer work deserves its own blog post (or collection of essays), but the point is: this experienced developer did not understand the cost of their contribution, and as a result makes the load on other maintainers higher rather than lower.

I can easily find NumPy or SciPy issues that I'd rather not see a fix PR for. They're valid bug reports, but the value of fixing them is minimal and the costs are high. Is NumPy 1.16 better than 1.15? Yes, but only marginally, despite the huge amount of work that went into it. If you don't believe me, read the [release notes](https://www.numpy.org/devdocs/release.html#numpy-1-16-0-release-notes): not one of the listed highlights is something the average user will remotely care about. 

Better news: this will not be true for NumPy 1.17 - it will have a completely new implementation of the `numpy.fft` module (significantly more accurate *and* faster) and a new random number generator infrastructure with several much higher quality generators. Now not everyone can just write a whole new submodule. But maintainers are capable of that, or of other equally important major improvements - if only they weren't too busy with reviewing!

I hope my argument has convinced you by now. If you care about helping an open source project, **here's a few things you should consider doing**:

1. *Ask yourself if the change really is needed.* Is it worth the effort - yours and the reviewers?
2. *Be explicit in telling the reviewer what the benefit is*, in your PR description. So not "this is faster", but "under these circumstances I see a 40% performance improvement, and here's how I benchmarked it".
3. *Offset the cost of your change proposal.* There's a number of ways you can do this:
  - You can review another PR in return for having yours reviewed (only if you know you are capable of doing that - confusing or incorrect reviews won't help!).
  - You can answer some user questions on StackOverflow.
  - You can donate to the project.

## Cost of a review comment

You can apply the same line of thinking to reviewing rather than opening a pull request. Excessive nitpicking is unfortunately common in open source projects. Yes, each comment has the potential to make the code or documentation a little more perfect, but is it really needed? Each comment is a request to a contributor to do more work. The first few sets of comments for a new contributor may be a good learning experience. After that, non-essential comments potentially frustrate a contributor and may cause him or her to leave or experience unnecessary stress. Instead, as a reviewer you should focus on the major issues: correctness, maintainability, performance, clear documentation, test coverage. Any typo, style issue, or equivalent-but-not-preferred code construct can also be fixed up by you as the reviewer (either push to the branch from which the PR was made, or fix it in a follow-up PR). Or even just ignore it and leave it for another contributor to tackle as a "good first issue".

The issue with nitpicking was driven home for me by two recent experiences. One was attending [Maintainerati](https://maintainerati.org/) (highly recommended unconference), where in a session on diversity several non native English speakers said they felt unwelcome by reviewers pointing out small grammatical issues in their doc PRs. The suggestions on what to do instead that I made above are what they said they would have preferred instead. The other one was a NumPy PR where I started noticing excessive back-and-forth comments and fixes on a PR that I wasn't directly involved in. It was a technically solid PR by a new and obviously capable contributor. It could have been merged after one round of review. Instead, review and rework cycles spanned over 100+ comments and two months. In the end I had to jump in to stop that pattern and finally get the PR merged. It wasn't pleasant for me to have to do, and I'm fairly sure the experience on that whole PR wasn't pleasant for anyone involved.

One way of addressing these issues with code review is for projects to write a reviewer guide, and provide feedback to reviewers in the same way as they do to contributors. Every project has a contributor guide; a reviewer guide is equally important.
