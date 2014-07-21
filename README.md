Proles - Moods of the Masses
=======

This repository contains a simple [Meteor-powered](https://the.meteor.com/) web application that pulls current trends from the [Twitter API](https://dev.twitter.com/) and uses [AFINN-based sentiment analysis](https://www.npmjs.org/package/sentiment) on the tweets (currently US-only to make language processing a little easier) related to the trend to provide a summary of its sentiment and keywords. You can check it out at [proles.net](http://proles.net/), and to actually run it yourself:

    curl https://install.meteor.com/ | sh
    npm install -g meteorite
    mrt create proles
    # clone this repo however you choose and stick it in proles/
    mrt start

Right now it's a pretty simple and minimal "proof of concept", but still interesting in that it gives a quick summary of popular things going on. Some natural expansions I'll hopefully get to pursue (in rough priority order):
- Finish figuring out Meteor subscription and reactive stuff so the trends automatically update without refreshing the page (and just generally clean up things, write tests, make sure the code is idiomatic, etc.)
- More language processing/cleanup - porting/stemming, stop words, etc. (the sentiment library does tokenize already but more processing may help)
- Incorporate other languages (and possibly translate to English for summary/homogeneity)
- Incorporate other sources of trends (news, other social media)
- Allow for user filtering/searching (instead of getting all trends, search for/view a specific topic and see what people are feeling about that, e.g. "Tech Trends")
- Time: show history (past trends), and possibly show what is trending over larger windows than just "right now" (e.g. like a weekly/monthly/annual "zeitgeist")
- Pull in better/more secondary information (recognize tags/geo data, have inline hide/show info boxes to provide brief summaries, etc.)

But overall, this provides a mostly clean starting point of a pure JavaScript web application, with a core of Meteor and Bootstrap and using Meteorite and NPM on top of Meteor to pull in other needed things (Twitter API, sentiment package). Thanks for checking it out!