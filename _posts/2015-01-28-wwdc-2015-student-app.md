---
layout: post
title: WWDC 2015 Student App
date: '2015-01-28T11:24:56-05:00'
tags:
- ios wwdc ObjectiveC swift
tumblr_url: http://sbastidasr.com/post/117607948834/wwdc-2015-student-app

subtitle:   "asdasd"
author:     "sbastidasr"
header-img: "img/wwdc/wwdcApp1.jpg"
---
**My WWDC 2015 Student App**

It’s that time of the year again! Excitement about new devices, leaks and thousands and thousands of new blog posts reviewing the releases. This year it is going to be all about the new MacBooks and how swift is catching up!

I applied to the student scholarship for the WWDC. If you win, you get tickets to the event (Which are not easy to get even if you are willing to pay for one). And, maybe flight and hotel expenses. It reads: “Use your creativity and coding skills to build and submit an app that tells us about you.” And it has to have, at least, something written in swift. Here’s what I came up with:

<a href="#">
    <img src="{{ site.baseurl }}/img/wwdc/wwdcApp2.png" alt="wwdc">
</a>

The goal was to make an interactive app that presents my life in a fun way. The first goal was to make a page-based app, where swiping left or right switches screens animatedly. A simple way to this was to use a PageView and switch between ViewControllers. But, this made all the screen receive touch events, but I only wanted some areas to add interactivity to another. For this, I created the base class SwipeViewController.h

**Color the World!**
The first interactive element is a page that allows the user to paint the world of colors on top of a white MacBook. The best way to do a coloring effect, in my opinion, is to cover the colored image with a white foreground that the user erases. First, I made the white template that contains the MacBook. Then, I had to get the drawing for the colored part (Big thanks to Rafaela Bastidas for helping me on this one!). To achieve the effect, I laid made a paint-like app, where the user “Colors” by painting the white image with clearColor.

For this, I made both an EraseView that contains both images and the pen width. I based this on a Ray Wenderlich tutorial that can be found here and a stack overflow post http://stackoverflow.com/questions/10032576/erase-and-un-erase-a-image-in-uiimageview-with-touch-using-coregraphics. The EraseViewController initializes the images and contains the labels for the output.

<a href="#">
    <img src="{{ site.baseurl }}/img/wwdc/wwdcApp3.png" alt="wwdc">
</a>

**Draw a Ruby!**
<a href="#">
    <img src="{{ site.baseurl }}/img/wwdc/wwdcApp4.png" alt="wwdc">
</a>

I wanted the user to interact with the app so, for web development, I made a screen where you have to draw a ruby to pass to the Information. This one was a bit more complicated the last ones, mainly because it involves many things. The first one is drawing the Ruby onscreen. The DrawViewController class achieves this. As I didn’t want to draw everything with bezier paths, I used PocketSVG to convert SVGs to paths. Then I animated the StrokeEnd

<a href="#">
    <img src="{{ site.baseurl }}/img/wwdc/wwdcApp5.png" alt="wwdc">
</a>

This one was fun. I used a gesture detector called WTMGlyph. This one had to be added, and correctly modified to recognize the ruby paths. The output of this lets you (or not) into the next screen.

**Shake the Tree!**

<a href="#">
    <img src="{{ site.baseurl }}/img/wwdc/wwdcApp6.png" alt="wwdc">
</a>

this one is my favorite! I took a picture of a tree my sister drew and vectorized it with photoshop. And yes, I could have made the lines smoother but there was little time. I completely removed the leave, which I then drew with red, circular leaves.

Shaking the iPhone makes the leaves fall off animatedly. Each one has a different speed and acceleration to get a cooler effect. This moves you to my awards screen. This is the LeavesViewController

**Enjoy a tune**

<a href="#">
    <img src="{{ site.baseurl }}/img/wwdc/wwdcApp7.png" alt="wwdc">
</a>

Finally, there is a music screen. it has a playable piano made in swift. This one was very easy. I got the key sounds from here.

And that is it!  Check the complete project on GitHub or follow me on Twitter for more @sbastidasr.
