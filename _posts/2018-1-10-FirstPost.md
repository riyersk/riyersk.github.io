---
layout: post
title: Project Benson Reflection
---

Last week, on Monday the 8th, I started at Metis, a data science bootcamp.  The first project was due on Friday, January 12th.

![_config.yml]({{ site.baseurl }}/images/config.png)

For this project, we had to advise an imaginary group, Women Tech Women Yes (WTWY) on the placement of their street teams at subway entrances for outreach for their annual gala.  These street teams were to invite people to register with their email addresses for a free ticket to their event.  WTWY wanted to target people who would come to their event and people who might potentially donate to their cause.  The data to be used was the MTA turnstile data freely available online, as well as any other data source we as a group thought might be useful.

My major contribution to our project was the data cleaning aspect.  My job was to download the data from the MTA website and clean it to get to a format for EDA (exploratory data analysis).  At first, we decided as a team to use March, April, and May data from 2016 and 2017, working out to 28 MTA files worth of data.  I eventually got this to work, but my code was taking a very long time to execute, and it became very clear that handling all this data in our project was not going to be realistic given our time constraints.  I went back to my group and insisted we only use May 2017 data, to which they agreed.

After delivering a clean data set to the group, I learned that our plan of action was to determine which stations were the most highly trafficked (top 30 or so), which stations were close to colleges and universities, and which stations were close to tech company offices, and find the intersection of all those sets.  We would then recommend to WTWY that their street teams go to those stations in that intersection of sets.  This seemed reasonable to me, and this is what we ended up presenting.

In our presentation, we chose 5 stations, and included a slide on each one, explaining why it was a recommended station. Each of these slides had a graph of the traffic through that station on a representative day.

The instructors' feedback had 3 main points:
  1) We focused too much on the recommendation and not enough on the process.
  2) The model we used to incorporate tech company and higher education data sort of got lost in the presentation.
  4) Having a slide on each station with the same type of graph got a little repetitive.
  
I agreed with the instructors' feedback.  Particularly, the algorithm we used to synthesize tech company and higher education data with traffic could have been much more rigorously defined.

As for how I personally could improve, I see two takeaways:
  1) Make sure I'm participating in group discussions on high level project layout.
  2) Get a sense for how much data a project should be using.
  
Regarding the first point, I volunteered to do the data cleaning, and then immediately sort of went to do it, without staying engaged with the rest of the group as the discussed how the data would be used.  After this project, I now think that everybody in a group should have a high level understanding of what direction a project is taking at the point when that direction is decided.  In the future, in a similar situation, if I were to volunteer to data clean, I would also make sure to stay engaged with any discussions regarding project strategy, rather than rushing off to do my part with no concern for anything else.

Regarding the second point, the fact that we originally tried to use 28 weeks of data really slowed us down.  I would estimate that it cost us at least 1 or 2 days, which is major when you only have a week to complete a project.  In the future, I would discuss projects with experienced people to get a sense of how much data is reasonable to use.
