---
title: "2018 NumFOCUS Summit - a summary"
date: 2018-10-13
categories:
- Python
tags:
- NumFOCUS
- NumPy
- roadmap
---

During 22-25 Sep 2018 I attended the [NumFOCUS Summit](https://summit.numfocus.org). It consisted of two 2-day parts: the Sustainability Workshop (attended by 1-3 maintainers of almost all sponsored projects), and the Project Forum (attended by a subset of those maintainers plus a number of key industry stakeholders).  I attended wearing two hats: as a member of the NumFOCUS Board of Directors, and as a maintainer of NumPy.  Besides me, NumPy was represented by Allan Haldane, whom I had the pleasure to meet in person for the first time.  In this post I'll focus on topics that are relevant to NumPy.  Most ideas/answers about NumPy in this post are mine, and not in any way "official NumPy policy".

## The NumPy Roadmap

During the Summit I gave two 15 minute presentations about the NumPy roadmap.  The first one ([slides](TODO)) was aimed at explaining how we constructed the NumPy roadmap, and what other projects could learn from the process we went through.  The second one ([slides](TODO)) was much more about the roadmap itself - what's on it, and why.

<insert image of hierarchy>

One valid criticism was about the "NumPy Scope" page.  That page starts with saying "this is not an aspirational definition of the scope of NumPy ..." - and the obvious question is: *why not*?  Other than that, the roadmap and ideas about different having both a technical and non-technical roadmap targeted at different audiences were very well received though.

Throughout the Summit I received a lot of *very positive* feedback on and questions about both NEP 18 (`__array_function__`) and the easier custom dtypes plan.  Many projects are interested in using either one or both of those features.  For example, there were a number of peiple discussing units libraries (unyt, TODO) - which would likely benefit from being able to use custom dtypes with units.

Looking at the state of the roadmaps of all projects, it's clear that there's a lot of work to do.  About half of the projects did not have a roadmap at all and of the ones that did, about half were out of date or very incomplete.  Finally no project had a clear non-technical roadmap.  As a community we still have a lot of work to do here ...


## What would NumPy do with funding?

A separate workshop session was held about funding.  It had synergy with the roadmap session, the most interesting exercise was "if you had funding for 3-5 years, what would you work on and how much would it cost?".  Here are the answers I came up with (MY == man-year, 1 person working full-time for a year):

1. Redesign numpy.org, as well as a broader (ecosystemwide) website.  Cost: 0.25 MY + $40k.
2. Implement and mature interoperability protocols (such as `__array_function__`).  Cost: 1-2 MY.  Should include at least one downstream adoption for sparse arrays, distributed arrays and GPU arrays.
3. A sustained positive balance of merged vs open PRs and closed vs opened issues.  Cost: 1 MY/yr on top of volunteer effort.
4. A community liaison for NumPy with rest of the ecosystem.  Cost: 0.5-1 MY/yr.

Other interesting questions with my answers were:

*What does NumPy need to sustain/survive?*
Time for: base level of maintenance, release management and leadership.
Funds for: a website redesign.

*What does NumPy need to grow?*

- 1 manager / community leader
- 2-5 full-time devs
- in-person core team workshops

*What could you do if you had more funds?*

- Grant/roadmap/vision/.... writing
- Building more industry relations & writing key user stories
- GSoC type projects (incl mentoring).  Paying for mentors' time is the critical part (in general, not limited to students).
- Cross-stack testing.


## Sustainability goals for NumPy

At the end of the sustainability workshop, we were asked to formulate one goal related to each of the workshop session topics.  Here is what we (Allan and I) came up with:

*First a meta-goal: we know that these are more goals than we can realistically achieve given time constraints of the people we need to take actions here. A key goal for us is to improve the bandwidth of those people over time, so we don’t have to say this same thing next year.*

Now the topic goals:

- Roadmap goals:
    - write the non-technical roadmap in the next 12 months
    - make clear(er) how the roadmap was constructed, and who was (and will be) involved
- Goal on governance: document who controls the direction of grant-funded people and how.
- Funding goal: 
    - contribute to a joint NumFOCUS proposal (as needed)
    - figure out if/how each core dev could use funding
- Infrastructure goal: make Azure Pipelines work (*note: already done!*)
- Culture/CoC goal: we just adopted a CoC, evaluate how that functions
- Unconference goal: take (positive) feedback on NEP 18 back to project (*note: see above in this post*)


## Other notes

It was interesting to see and discuss new business models that aim to make open source more sustainable by giving maintainers more options to get paid.  E.g. Quansight, Tidelift and Open Source Answers, which all have different (and complementary) aims and models.  I intend to write about this in more detail later.

Corporate programs to match employees' giving to charity can be an interesting source of project income as well.  E.g. Microsoft will donate $25 to a project for every hour that one of its employees works on that project, via Benevity.

Steve Dower gave an interesting talk/demo of Azure Pipelines.  Microsoft really does seem committed to giving back to the open source community, and I'm happy to see that we already have adopted Azure Pipelines as part of the NumPy CI setup.  Another interesting feature (that we don't yet use) is that Azure offers private PyPI servers (could perhaps remove the need for maintaining wheels.scipy.org?).


## Conclusion

The Summit was a great experience for me this year.  Not everything went well and on the last day I ran out of steam, but I would recommend anyone going next year if given the chance.  I've met a large number of interesting people, and learned about new tools, business models and project maintenance ideas. Finally having to present twice on the NumPy roadmap really forced me to think about where the project is (or could be) going.
