---
title: "Modularization and why I suck at it"
date: 2022-12-14T22:26:08+01:00
---

This isn't obviously a new topic, I've somehow skipped it, because it was hot at the time I was still junior dev and I wasn't ready to dive in any architectural topics. Back then I was working on rather small to medium sized products that wouldn't needed it.

The larger the product gets the more it would benefit from a proper modularization.
At some point of my developer career I thought that a good architecture pattern would be enough for maintaining a project. 
The lack of knowledge how to properly divide app into modules was quickly revealed as I worked on some bigger projects.
In fact there is a long way to go before I could say that I'm familiar with the topic enough to guide another people.

1. The main questions I asked myself was why should I do it? 
2. How it can be done? Is there any silver bullet or guide how to do it properly?
3. What are the possible problems with this approach?

## Why should I do it?

At some point in the product development you would see that handling one single repository will be painful.
If the project is big and contains lots of features:
* it probably takes a lot of time to build
* there are dozens of merge requests that may cause solving merge conflicts often
* it's hard to align with all feature specific logic (so often huge teams start to divide to feature-based teams)
* reusability - if you have for example more than one product you can share one module between two apps, if you have chat feature you can create configurable module out of it and reuse it among projects.
* having huge team responsible for whole app is hard, instead you can divide it into feature-teams so each team will be familiar with their own smaller part of code.

## How it can be done?

First of all if you have already more-less clean architecture you should consider create modules that are not feature-based like Networking. Then the hardest part will be creating feature modules. This might be tricky at the beginning to precise how big should module be. Each app has it's own features, feature-model could be f.ex. a chat, payments integration, onboarding, etc. It's really up to you which logic would you like first to be reusable.

## What are possible problems with modularizing?

You need to know it won't be a quick task to be completed within one sprint. Each product is different and first step will be a meeting or several to discuss how to handle it. To look at the code, describe starting points, which modules will app need first.
Your product owners will have to agree to take one or two people out of implementing features for some sprints to take care of modularization. 
It may become complex and time consuming, you'll probably need to refactor some parts of code (that is actually on a pros side), add tests.
