---
layout: page
title: Summer 2016 - Internship at Hiperware Pte Ltd
permalink: internships/summer-2016/
subtitle: Internship at Hiperware - Summer 2016
---

### Background

Hiperware is an app development company, founded in 2006. Hiperware's ClassHero
(previously Learn and Earn) is a platform for practice and assignments that ties
learning goals to rewards that can be earned on completing the goals.  These
rewards can be items on Amazon, iTunes, or a trip to the local museum.

### Project

* Port the [iOS
app](https://itunes.apple.com/us/app/learn-earn-app-for-math-motivate/id1028326954)
to Android, API Level 15+.
* Connect the Android client to the existing REST API (built using ExpressJS)
* Replicate design to ensure consistency for users who are using iOS as well as
    Android variants
* Connect the app to In-App purchases on both Play store and Amazon store, to
    enable the subscription-based business model of the application
* Create 2 build variants for the Google Play Store and Amazon App store for
    Amazon Fire OS tablets

### Results

The completely functional port was completed. The app was released on the two
stores in January 2017.

[Play
Store](https://play.google.com/store/apps/details?id=www.hiperware.website.learnandearn.play) ||
[Amazon App
Store](https://www.amazon.com/Learn-Earn-app-math-everyone/dp/B01HBQ8KPW/ref=sr_1_2)

### Challenges

* **Replicating design on Android:** iOS has to deal with only one resolution
    and a fixed set of screen sizes. iOS' AutoLayout takes care of this, and any
    element can be placed anywhere. However, Android has a box model and has to
    support a myriad list of screen sizes, resolutions and aspect ratios. If the
    design had to be replicated, then the smallest 4:3 screen inset of the
    screen needed to be found out, and the app can only work inside that space.

    ![img](/assets/img/hiperware/aspect-ratio-demo.png)

* **Several types of questions:** There are many types of questions (such as
    _Multiple choice_, _Fill in the Blanks_ or _Drag and Drop Objects_). These
    types of question are implemented as "widgets" which are dynamically chosen
    at runtime, depending on the type of question returned from the backend.
    These widgets are all rather involved, UI-wise. I was able to implement 9
    widgets during my time at Hiperware.

    ![img](/assets/img/hiperware/widget-dd-1.png)

    The items on the right side can be dragged and dropped into the two
    containers, so as to build the answer to the question. 
    
    For this question, 62 = 6 * 10 + 2 * 1

    ***

    ![img](/assets/img/hiperware/widget-textbox.png)

    The coordinates of where to place the textbox will be sent as part of the
    metadata for a question. The frontend must then place the textbox at the
    appropriate location.

* **Android API Levels:** As the API levels increase from 15, the Android
    SDK becomes more and more robust, hence being able to handle more memory
    intensive operations (such as bitmap loading). But to support API Level 15,
    code must always be very careful about loading bitmaps or any other heavy
    operation because it might lead to an Out of Memory exception, which is
    really bad UX.

* **Caching of images and session information:** There are several types of
    caching required for management of the various features and logins that can
    be done on the application. This data needs to be cached on disk in most
    cases, but when there is an ongoing session, the data should be cached in
    memory providing fast access.

    To solve this problem, I used a multi-backend caching library that
    maintained a limited resources LRU cache in memory and a disk cache where
    the values are dumped in case they have to be evicted from the LRU cache.

### Process: Tools and skills

* Used RetroFit and Volley as the REST API clients
* Used Gson for String -> JSON serialization and de-serialization
* Used a caching library that maintains a disk and memory LRU cache
* Used the Universal Image Loading library for loading and caching images from
    AWS S3 and it's CDN

### Some more screenshots

![img](/assets/img/hiperware/welcome-screen.png)

Home screen. The first screen a user sees on opening the app.

***

![img](/assets/img/hiperware/parents-reward-selection.png)

Parents Rewards selection screen. Parents can decide the list of rewards that
they want their kids to be able to pick from.

***

![img](/assets/img/hiperware/kids-welcome.png)

Kids Welcome screen. After logging in, this screen is shown to the kids.

**Bonus:** look closely at the calendar in the background, it is dynamically
updated to make sure that the present date is shown! It is an Android
TableLayout with the appropriate highlight. This screenshot was taken on Thursday,
2nd June, 2016.

***

![img](/assets/img/hiperware/kids-skill-selection.png)

Kids Skill selection screen. Kids can select the skill that they want to
practice on this screen.

***

![img](/assets/img/hiperware/kids-practice-1.png)

Kids Practice Screen. After the kid selects the kid they want to practice, this
is the screen that loads and shows the question.

***

![img](/assets/img/hiperware/kids-practice-2.png)

Kids Practice Screen. This is yet another of the widgets that places a textbox
at appropriate positions on the screen depending on coordinates sent by the
backend.

### Some statistics

**Duration:** May 2016 - August 2016  
**Project:** Port Learn and Earn, the iOS app to Android, targeted at tablets, API 15+  
**Working hours (flexible):** 10 am - 6 pm, 5 days a week
