---
layout: essay
type: essay
title: Assignment 3 Retrospective
# All dates must be YYYY-MM-DD format!
date: 2020-12-18
labels:
  - programming
  - javascript
  - server
  - web development
  - retrospective
---


Assignment 3 was by far the most challenging of all the assignments so far. That being said, it was also a lot of fun to push my understanding of how data flows across the front and back end. I never really realized how complicated things can get very quickly. A new little feature here means a little change here, there, and everywhere! 

I worked alone on this assignment and I think it really helped me keep track of the flow of everything. I would be interested in splitting up some work and seeing how it goes in the future, although for some things I wonder if it would really speed up the process or slow it down by trying to constantly communicate changes or how one bug or new feature (or both) affect some far-flung reaches of my site. I felt like a detective a lot of the time trying to back track and find out where things where going wrong, or even worse, unexpected right!

In the end, I ran out of time to really put some polish on the site, and my code is a horror to look at I'm sure. I committed some cardinal sins by using the same code in different places instead of reworking it to use less code more modularly. I ran into an issue with trying to display my shopping cart from my session data and it took me over an hour to figure out. I thought I was being clever by making my shopping cart almost a mirror of my product data JSON file so that I could somehow just plug one in for the other when the time came. There are some interesting projects going on I learned about to try to do stuff like that, but none I could apply (or figure out how to) in time to include in this project. In the end, I went with an admittedly ugly solution by iterating through three layers of for-loops. I think that makes it O(n^3), which thankfully doesn't really matter with how few products I have to display, but I can't stop thinking about how I could do this better if I had more time to think about it.

At the end of the day though, the site works with no problems, and I like how it turned out. If I had more time, I would have liked to spend more time getting the CSS set up to be a bit more pretty and maybe use more images, especially on the menu page where it's just text. Overall, I had a good time with the site and I'll be missing CPU City.
