---
title: A Complete Guide to useEffect
image: squares.gif
description: Components
---

March 9, 2019

You wrote a few components with Hooks. Maybe even a small app. You’re mostly satisfied. You’re comfortable with the API and picked up a few tricks along the way. You even made some custom Hooks to extract repetitive logic (300 lines gone!) and showed it off to your colleagues. “Great job”, they said.

But sometimes when you useEffect, the pieces don’t quite fit together. You have a nagging feeling that you’re missing something. It seems similar to class lifecycles… but is it really? You find yourself asking questions like:

🤔 How do I replicate componentDidMount with useEffect?
🤔 How do I correctly fetch data inside useEffect? What is []?
🤔 Do I need to specify functions as effect dependencies or not?
🤔 Why do I sometimes get an infinite refetching loop?
🤔 Why do I sometimes get an old state or prop value inside my effect?
When I just started using Hooks, I was confused by all of those questions too. Even when writing the initial docs, I didn’t have a firm grasp on some of the subtleties. I’ve since had a few “aha” moments that I want to share with you. This deep dive will make the answers to these questions look obvious to you.

To see the answers, we need to take a step back. The goal of this article isn’t to give you a list of bullet point recipes. It’s to help you truly “grok” useEffect. There won’t be much to learn. In fact, we’ll spend most of our time unlearning.

It’s only after I stopped looking at the useEffect Hook through the prism of the familiar class lifecycle methods that everything came together for me.

“Unlearn what you have learned.” — Yoda
This article assumes that you’re somewhat familiar with useEffect API.

It’s also really long. It’s like a mini-book. That’s just my preferred format. But I wrote a TLDR just below if you’re in a rush or don’t really care.

If you’re not comfortable with deep dives, you might want to wait until these explanations appear elsewhere. Just like when React came out in 2013, it will take some time for people to recognize a different mental model and teach it.
