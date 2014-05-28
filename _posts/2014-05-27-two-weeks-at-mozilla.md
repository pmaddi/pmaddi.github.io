---
layout: post
title:  "Two weeks at Mozilla"
date:   2014-05-28 17:00:00
categories: mozilla intern
excerpt: "The release dashboard in its current state helps release managers find critical bugs. Perhaps it could provide greater insight into the release's health with these integrated metrics.
"
---
I'm two weeks into my Release Management internship at Mozilla. So far, it has been an incredible experience. 

![The glorious firefox](http://news.worldwild.org/wp-content/uploads/2008/09/red_panda.jpg)
<p style="text-align: center">The majestic red panda basking cherishing the open source world</p>

For the uninitiated, release managers make sure the right code gets into the codebase. Mozilla ships updates often--Firefox every 6 weeks. We make sure that important features and stable patches ship. Among other things, this involves deciding what bugs and features are critical for the release and ensuring those get completed.

This summer, apart from helping managing a few releases, I'll be working on my intern project, the release management dashboard.

## The dashboard

It would be convenient to have an idea of how a release of Firefox is coming along by glancing at a single page. 

[Willie][Willie], the previous intern on the team has made great progress on a dashboard that does just this. Currently his [dashboard][rrdash] can create charts of key bug metrics. This handy tool can generate a timeseries from any bugzilla query.

![Release readiness dashboard]({{site.url}}/assets/images/rrdash.png)
<p style="text-align: center">The release readiness dashboard, by Wille</p>

[Bugzilla](https://bugzilla.mozilla.org/) is the vessel of _Agile-ness_ by which Mozilla keeps track of bugs and feautres. For instance, one can currently track the number of bugs marked by the _crasher_ tag, which lends the release manager some insight on what bugs to pay attention to. But bugzilla only gets you so far. 

If release health is your concern, bugs are a noisy feature of your hidden variable. The number of crasher bugs doesn't directly correlate to user experience, since humans must input bugs into bugzilla. There's a delay between when the problem patch lands and the bug is filed. Plus, the bug doesn't relate the number of users affected. To get an idea of how much Firefox is crashing, _look at how much Firefox is crashing_.

Luckily, Mozilla tracks the [number of daily crashes](https://crash-stats.mozilla.com/home/products/Firefox)! We track key performance metrics too, including 

- startup time
- graphics performance
- cold launch time (for Firefox OS)
- idle power usage (for Firefox OS)

... just to name a few. 

Right now, these data live on databases managed by different teams. It would be pretty neat to see these data within the [dashboard][rrdash].

The dashboard in its current state helps release managers find critical bugs. Perhaps it could provide greater insight into the release's health with these integrated metrics.

[Willie]: http://blog.williecheong.com/
[rrdash]: https://release-dash.paas.allizom.org/