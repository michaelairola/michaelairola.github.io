---
title: Side Project Breakdown
tags: breakdown side-projects projects
---
Hi everyone! Chances are if you are reading this post, you either interviewed me recently or are looking for a viable candidate for a job opportunity and want to know what I've been up to in my spare time (I would love to share code that I've written professionally for companies, but legally that's a tough one - especially since I currently work in the healthcare industry. HIPAA and othere gov' regulations are kind of a big deal 🤷 ).

If you like any of these ideas and have suggestions, or would like to try to work on the code snippets I have, let me know! <a href="mailto: me@michaelairola.com">Email me</a>.

### Highlight helper
During my 2 year sprint up in the bay area (not the bay area most people think of, which is San Fransisco. I was in the heart of Silicon Valley: Sunnyvale, Mountain View, San Jose etc.) I met a lot of really cool people who are passionate about what they do and love to create. One friend I met through beach volleyball, <a target="_blank" href="https://github.com/gruns">Ansgar Grunseid</a> was CEO of his own creation; A peer-to-peer content and delivery network in the form of a website widget - <a target="_blank" href="https://arc.io">Arc</a>. 

Ansgar was super busy with, you know, being a CEO, but he had an idea that turned into a pretty fun side project; The Highlight Helper! Ansgar wanted a widget (he loves widgets) that would help with obtaining user-provided feedback on websites. The goal: if a user were to highlight text on a website, a popup would appear with a text input and a "Send email to website owner" button. This would then send an email to the website creator with information on the page, highlighted text, and the note that is sent. 

Sounds simple enough, and I was about a year into being a professional developer, so I decided to hack it up <a target="_blank" href="https://github.com/michaelairola/HighlightHelper">here</a>. The project was never finished, and looking back I don't think I was ready to create a finished product that users could reliably use by myself. But this project did teach me a few things: 

1. I was able to hone in (and probably focus a little too much) on dev ops, specifically development testing environments and boilerplate setups. Looking back, this was a good learning experince for me, but on a viable product with real end-users it would be nice to spend less time on trivials such as these. 

2. I learned this very important lesson: "Never re-invent the wheel". When I was first creating the widget, my focus was on getting the popup to appear where it needed to. This was dependent on a lot of variables and was very much tied to how the client read the website. I learned probably a little too late that there are <a target="_blank" href="https://www.npmjs.com/package/@popperjs/core">already solutions for this</a> and I could have spent my time elsewhere, developing the ui of the popup or implementing a variable approach. 

All in all, a fun idea and a good experience to write. Unfortunately, like 90% of other side projects in the known universe, work picked up and I lost site of completing this one. It would be fun to spend a week or so from scratch on this idea, but alas there are always bigger fish to fry. 

--------------------------------------------------------------------------
After my stint up in the bay, I quit my job and was fun-employed for about 6 months or so. During this time, I did a lot of traveling and recreationally-focused activities, but it was hard to stay away from creating things and playing around with new frameworks. I really got into publishing more of my ideas and put together a few content-based servers: a <a target="_blank" href="https://cookboook.michaelairola.com">Recipe Book</a> for all of the recipes I like to make, and <a target="_blank" href="">this blog</a>. On the blog, I wanted to be able to post <a target="_blank" href="https://blog.michaelairola.com/2022/02/12/side-project-breakdown.html">data-driven</a> thoughts (it really turned into more of a public diary, but hey at least I'm writing more). 
 
### Pew Search
This brings me to the next side project I worked on - <a target="_blank" href="https://limitless-sea-00058.herokuapp.com/">Pew Search</a> (code <a target="_blank" href="https://github.com/michaelairola/pew-search">here</a>)! The goal of this was to provide a better UI and question-framing setup for the Pew Research Website's <a target="_blank" href="https://www.pewresearch.org/question-search/">question search page</a>. The main two things I focused on with this project are: 

1. Reverse-engineering the API! This took a little bit of hacking, as the api required a special token that was embedded in the html of the original website. I had to setup a reverse proxy within my server that went to the Pew Research website to grab the token, and from there I had to also reverse proxy the query api itself (Protections in browsers made against <a target="_blank" href="https://owasp.org/www-community/attacks/xss/">XSS</a> attacks do not allow unauthorized websites to access information from servers, so the server had act as a middle man: Browser/client => Pew Search server => Pew Research website api). A little convoluted, but it worked out decently well and it was a fun excercise.  

2. Providing a cleaner UI. The original website felt a little clunky to me, and the question phrasings weren't at all clear. I decided a cleaner look and a couple React CSSTransition components would give it a smoother feel. I also wanted to use some text anyalsis logic to try and clean up the questions (this was a tough problem to solve, and the solution has a lot of holes in it currently. I put together a few base test cases that I wanted to make sure worked out - a more complete solution would probably have more of these). 

If I had more time, I think it would be fun to try and implement the question phrasing logic more. This is a classification and rearrangement issue, with different questions being categorized into different question types and from there different transformations of the text would occur. The first part might have solutions in machine learning (nlp to be exact), and it would be fun to explore different algorithms that could solve it. 

### Birthday Ping

This <a target="_blank" href="https://github.com/michaelairola/Birthday-Ping">App</a> was my very last idea before getting hired at my current job (I tell myself that's why I never finished it :/). I wanted an application that could connect to as many outside sources as possible and collect contact birthdays, while at the same time providing a platform for collecting gift ideas and sending birthday wishes. 

I ended up putting the app together with <a target="_blank" href="https://expo.dev/">Expo</a>, real easy framework on top of React Native. This helped me concentrate on syncing with contacts and creating a fun UI with a dark mode implemented! 


If I have spare time in the future, it would be nice to work on connectig to other social media applications (facebook, instagram, ect) to get friend's birthdays information. It would also be cool to work on the gift section - I've always wanted to be better at giving gifts and having an application like this would be really beneficial in my life for this exact reason (which is why I wanted to put the app together in the first place). 



Well these, are 3 of my side projects. Stay tuned, I might have more in the future! Thanks for reading :) 
