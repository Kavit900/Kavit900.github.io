---
layout: post
date: 2016-09-29
title: Triangle Number Sequence 
---

Hi everyone, writing this post after a long time. I am writing this post again after so many days on the 
request of someone close to me. So currently, I am in Boston figuring out what I want with life but ya 
that can wait, I will write an emotional post some other day lol !

So today I and my two special friends came across an interesting problem. So in that problem we were given a number n and 
we need to find in how many rows this number can be arranged and in each row how many numbers you can place has a constraint.
Like we have to arrange that number n in n rows in such a way that 1st row would get 1, 2nd row would get 2 and so on.
So according to the problem we had to find the number of the row that would get fully completed with the given number n.

So basically on investigation you will see that the list is formed like this:-

> 1st row - 1 item.
> 2nd row - 2 items.
> 3rd row - 3 items.
> 4th row - 4 items.

In short if we clearly see then, after 1st row total elements is equal to 1, 2nd row is 3, 3rd row is 6... 
In a way after each row the total number of elements is equal to 

> (n * (n + 1) ) / 2

So, now in the problem we are given the above value and we had to find the row number, so basically the row becomes something like,

> n^2 + n <= given_items_number * 2

So, after making changes to the above quadratic equation, we get another relation as

> n = (sqrt( 8 * given_items_number) - 1 )/2

And this is the solution of the above mentioned problem.

I hope, this somewhat makes some things clear about triangle number sequence and next time whenever you see a series like this you will 
have an idea about what logic to implement. 