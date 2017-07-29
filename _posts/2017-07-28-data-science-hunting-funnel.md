---
layout:     post
title:      Data Science Hunting Funnel
date:       2017-07-11 00:00:00
time:   5
summary:    Machine learning must be combined with domain expertise to increase the probability of finding malicious network traffic.

categories: network traffic threat data science hunting funnel machine learning domain expertise

author: austin_taylor
author_github: austin-taylor
---


![MINUTE_BEACONS]({{ site.base }}/images/ds_hunting_funnel.png){: class="center-image"}

Today, we often hear about machine learning being applied to cybersecurity. 
The data science hunting funnel was created to illustrate a workflow for security researchers
and data scientist to help reduce their dataset and have the best likelihood of
identifying malicious traffic.

Hunt Funnel Breakdown
---

_Values are approximations_
* **Network Traffic** - Bits flowing into the funnel ready to be processed.
* **Produced Naturally** - Generated naturally by network users and devices. Represents all of your _normal_ network traffic. 
* **Machine Learning** - After applying machine learning, you can reduce your set of data to a much smaller subset by identifying _anomalies_. I chose 10% to represent help loosely illustrate the smaller subset of data after applying machine learning. A few examples include:
    * Identify periodic communication in the network in an attempt to identify an infected computer using command and control.
    * Applying the markov model to user agents with the lowest likelihood of occurrence. 
    * Identify DNS requests with high entropy or are identified as DGA using [Flare](https://github.com/austin-taylor/flare)
* **Domain Knowledge** - Once you have you have reduced your dataset using machine learning, domain expertise must be applied to further reduce the dataset to approximately 1-5% of total network traffic. This is where the _interesting_ results live. By interesting, I mean results that are anomolous to the network and did pass common questions an analyst might ask of network traffic. Depending on the protocol you're analyzing, you can apply practices such as:
    * Is this domain in Umbrella, Majestic or Alexa Top 1 million?
    * Is this IP a known TOR node
    * Does this domain have any blacklist or threat intelligence association?
    * Who owns this IP space? 
* **Potential Bad** - Finally, your data is ready to hunt on. The value .001 is meant to set expectations that finding malicious traffic, especially in larger networks, is very difficult. It requires the right amount of data science and domain expertise.
    * If you look closely, _bad_ is written at the bottom of the funnel. It's a bit hard to see because, like reality, finding evil in networks can be very difficult.


Below are slides from my presentation at [Data Intelligence Conference
Practitioner Focused Machine Learning](http://www.data-intelligence.ai/) where I applied the Data Science Hunting funnel to results to identify beaconing and DGA.

Slides from Capital One Presentation
------------------------------------

<iframe src="//www.slideshare.net/slideshow/embed_code/key/IlTAgqo2wgVLkJ" width="595" height="485" class="center-image" frameborder="0" marginwidth="0" marginheight="0" scrolling="no" style="border:1px solid #CCC; border-width:1px; margin-bottom:5px; max-width: 100%;" allowfullscreen> </iframe> <div style="margin-bottom:5px"> <strong> <a href="//www.slideshare.net/AustinTaylor8/threat-hunting-with-data-science" title="Threat Hunting with Data Science" target="_blank">Threat Hunting with Data Science</a> </strong> from <strong><a target="_blank" href="https://www.slideshare.net/AustinTaylor8">Austin Taylor</a></strong> </div>

Have you applied data science to network traffic? What has your experience been? Share in the comments section below!