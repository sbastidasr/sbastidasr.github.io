---
layout: post
title: What are CocoaPods? And why use them
date: '2015-07-09T14:32:54-05:00'
tags:
- cocoapods
- ios
- objective-C
tumblr_url: http://sbastidasr.com/post/123656473004/what-are-cocoapods-and-why-use-them
---
When I started on iOS development, nobody told me to use CocoaPods, and that it the reason why I am writing this post. If you use them, great. If not, hang in there. Here is my reason for using them.

<blockquote>CocoaPods is the dependency manager for Swift and Objective-C Cocoa projects. It has almost ten thousand libraries and can help you scale your projects elegantly.</blockquote>

So, what is a dependency manager?  It is a program that standardizes the way you use libraries. And, if you’ve added libraries on Xcode, you know the meaning of true pain. This is the compiler screen that precedes a million compiler errors.

<a href="#">
    <img src="{{ site.baseurl }}/img/tumblr_inline_nr8gnllLKD1tq2y7o_1280.png" alt="Post Sample Image">
</a>

Now, what if you are developing with a team. Usually, projects use certain versions of libraries. All developers would have to specify, download and install the exact version of the needed library. An update may break other’s build and so on. The Podfile standardizes this. Add it to your git and done. Everything is handled for you.

Adding/Deleting dependencies becomes as simple as adding them to the Podfile and installing. Dependencies between libraries are automatically handled.

<a href="#">
    <img src="{{ site.baseurl }}/img/tumblr_inline_nr8gnrInxC1tq2y7o_1280.png" alt="Post Sample Image">
</a>
<span class="caption text-muted">**Sigh, errors.**</span>


Especially, if you are using libraries like Parse on your apps: you will get about a 100 of these if you add more dependencies:
<a href="#">
    <img src="{{ site.baseurl }}/img/tumblr_inline_nr8gty3MoU1tq2y7o_1280.png" alt="Post Sample Image">
</a>
<span class="caption text-muted"><a href="http://stackoverflow.com/questions/24298144/duplicate-symbols-for-architecture-x86-64 ">StackOverflow Question</a></span>


So… removing flags actually fixes the problem but maybe some other libraries need those flags.

**How to solve this using CocoaPods**

Install CocoaPods on your machine
<blockquote>
$ sudo gem update –system <br>
$ sudo gem install cocoapods <br>
$ pod setup
</blockquote>

**Initialize Pods on your Project**
<blockquote>
cd into your projectfolder: cd ~/cool/app/Folder/ <br>
pod init <br>
open -a Xcode Podfile
</blockquote>

Write this on your file, with the pods you want to add. In this case WYPopover from git and Parse.

<blockquote>
platform :ios, ‘6.0’ <br>
pod 'WYPopoverController’, :git => <br> 'https://github.com/nicolaschengdev/WYPopoverController.git’
pod 'Facebook-iOS-SDK’ <br>
pod 'Parse’ <br>
pod 'ParseFacebookUtils’ <br>
</blockquote>

Open your terminal once again and
<blockquote>
pod install
</blockquote>

It will tell you to use the workspace and not the project from now on.
<blockquote>
YourApp.xcworkspace
</blockquote>

**Done.**
