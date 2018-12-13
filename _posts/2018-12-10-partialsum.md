---
layout: post
title:  Partial Sum in Haskell
date:   2018-12-10 22:36:00 -0800
categories: haskell code functional
author: Sandeep
---

For a series of numbers, a partial sum is a new series whose *i*th element is the sum of the first *i* numbers in the original series. 

I've been attempting to tackle Advent of Code with Haskell, and not doing a great job of keeping up: I'm not as Haskell-fluent as I'd like. But it's a lot of fun, and every day I convince myself I'm a little faster and a little more conversant with Haskellisms. 

For one of the earlier AoC problems, I found myself writing a function to compute partial sums, and was quite pleased with the result. Here it is:

{% highlight haskell %}
partialSum :: [Int] -> Int
partialSum [] = []
partialSum [x] = [x]
partialSum (x:xs) = [] + partialSum ([x + head xs] ++ tail xs)
{% endhighlight %}

Then I discovered there's a shockingly compact (also idiomatic and built-in) way to do this, involving `scanl` (a cousin of `fold`, apparently). 