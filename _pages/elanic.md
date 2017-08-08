---
layout: page
title: Summer 2017 - Internship at Elanic
permalink: internships/summer-2017/
subtitle: Internship at Elanic Bangalore - Summer 2017
---

### Background

[Elanic](http://elanic.in/) is a start-up based in Bangalore, founded in 2015.
Elanic's Android and iOS application provide a platform for buying and selling
pre-owned items. The focus of this platform is to make the process to make money
from a pre-owned item dead simple, hence bringing more and more people into this
market, both as sellers and buyers.

### Timeline

* Week 1: Get familiar with the existing ExpressJS backend code
* Week 2: Implement minor bugfixes
* Week 3-5: Take up some larger features and take it from design to implementation
* Week 6-8: Implement the Groups feature to add a social aspect to the buying
    experience (think Facebook Groups)

### Results

* Implemented the Groups feature starting from scratch. It was a feature
    complete groups implementation with user search in groups, group search, and
    anti-spam capabilities. Search was implemented using ElasticSearch's full
    text queries.

* Implemented a system to filter out spam in comments based on Regex-based
    rules, and daily/weekly limits on the type of comments that people can post.
    This feature was pushed into production in June 2017 and it has reduced the spam
    on the app manifold.

    (People posting _Checkout my closet_ across the app and people trying to
    share their phone numbers, in an attempt to circumvent the commission
    imposed by Elanic, were some of the types of comments that were reduced to a
    great extent by this spam filtering system)

* Enabled login and signup using just a mobile number. An OTP is sent to the
    mobile and the user profile is bootstrapped. This reduces the barrier to
    joining the app, by removing steps like _Email verification_.

* Fixed a bug in the order tracking apparatus. This bug was causing orders to go
    into an unresolvable state because of incorrect sorting order. After fixing
    this bug, there were no such unresolvable orders and it eased the operation
    of the Elanic logistics hub.

* Designed and deployed the _Ban a device from accessing the app_ feature. This
    feature is required and particularly useful in tackling bad actors on the
    app, who would sign up for multiple accounts from the same device in an
    attempt to sell fake products or scam other users.

* Designed the Angular-based admin panel frontend for taking action on abuses
    that have been reported by other users of the app. Also, made significant
    changes to the backend to enable the new frontend to work.

### Statistics

**Duration:** May 2017 - June 2017
**Working hours (flexible):** 10 am - 7 pm, 6 days a week
