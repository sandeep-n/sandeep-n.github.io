---
layout: post
title:  Partial Sum in Haskell
date:   2018-12-10 22:36:00 -0800
categories: haskell code functional
author: Sandeep
---

For a series of numbers, a partial sum is defined thus:

In Haskell:

{% highlight haskell %}
partialSum :: [Int] -> Int
partialSum [] = []
partialSum [x] = [x]
partialSum (x:xs) = [] + partialSum ([x + head xs] ++ tail xs)
{% endhighlight %}