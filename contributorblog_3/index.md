# Contributor Blog #3: Interview with Harish Pillay


We have many diverse contributors in opensource that help upstream communities in unconventional ways, which doesn’t require any coding or development skills. Starting with a non-code contribution can help anyone overcome the sense of failure and not being good enough, and it can also serve as a springboard for our open source adventure. This interview series aims to highlight some non-code open source contributions that anyone can make right now to get started contributing.

For this month’s edition, we talked about open source principles of contribution and collaboration with Harish Pillay.

<a href="/images/unconventionalcontributors/contributor_3/contributor_3.png" target="_blank"><img src="/images/unconventionalcontributors/contributor_3/contributor_3.png" width="300px" height="350px" align="right" /></a>


<br/>

**Thank you for taking some time out and interacting with us, Harish. You have been at Red Hat for as long as I can remember. Can you give us some background about what your journey has been at Red Hat and what you do today?**
<br/>

I'm Harish Pillay and I'm a Principal Community Architect based out of the Red Hat Singapore office. I’ve been at Red Hat now for almost 19 years. Yes, it is a long journey, but meaningful from my point of view. The bigger picture is what needs to be kept in mind as we go about enabling and empowering open source technologies and software. This is coupled with technical collaboration both in software and hardware. The Red Hat Singapore office was setup in my SOHO (small office home office) in 2003. In 2004, the Singapore office became the Asia-Pacific headquarters with the help of the Singapore Economic Development Board. 

I had, at the start, been running Red Hat Singapore as a one-man show as the Chief Technology Architect. I did everything from tech support to sales, to marketing, to speaking at conferences, etc. It was a little simpler because we only had to deal with one product - Red Hat Enterprise Linux. And since then, as we know, Red Hat has evolved and open source solutions got deeper into the proprietary software stack. You find a lot more services and options showing up as open source now, whether from us or someone else. So, from my point of view, it was not so much about a contribution to open source projects in and of itself directly. It is about building the bigger ecosystem of opportunities.

<br/>

**It’s almost a lifetime that you have dedicated to the Red Hat Singapore Office and building an open source ecosystem. What has your experience been in being a contributor?**
<br/>

My earliest code contribution was sometime in 1982 – see the blog post about stuff done then:<br/> 
[https://harishpillay.wordpress.com/2018/06/03/and-they-are-online-now/](https://harishpillay.wordpress.com/2018/06/03/and-they-are-online-now/)

I have contributed to so many places, I don't even know where it was, so I actually have no easy way to track it. These were the days before you had things like GitHub and GitLab and things like that. From a contributor’s standpoint, my claim to fame dates back to 1999. What happened in 1999 specifically just before Red Hat IPO’ed on Nasdaq, the Red Hat leadership and marketing team then looked at all the code that was being shipped at that time, which was Red Hat Linux, and extracted the email addresses and contributor names - from how-tos, kernel code, in Apache, etc and whatever was inside the distribution. These were collated into a contributors list and emails were sent to each one offering shares in Red Hat stock! Red Hat was the first one to do such a thing then (it was repeated by VA Linux some months later when VA Linux IPO’ed). 

So I received an email saying that I have ten shares from this entity called "Red Hat". Who was this company? Frankly, I had no idea. And why did I receive it? All because I had written code and I forgot about it. I had written a [how-to on IP aliases](http://linuxdocs.org/HOWTOs/IP-Masquerade-HOWTO-8.html). It was a very pleasant and thoughtful gesture of Red Hat to acknowledge contributors. Those docs/how-tos have been translated into many languages, and I've received email requests for help in French, Mandarin, Spanish, Japanese, and Russian.

IP aliases was about having one network card to respond to multiple IP addresses. This was a tricky thing to do, but IP aliases allowed you to then have one server to serve multiple IPs, and each IP has its own web server associated with it. All of this predates Apache httpd itself adding virtual hosts. 

I have another “starting” point as well. I would go all the way back to when I was in graduate school in Oregon State University in the mid-1980s. Probably in 1986, I was working as a Teaching Assistant in the Department of Electrical and Computer Engineering and I received a tape from the Free Software Foundation. It contained a copy of emacs. I had no idea what that was about - yeah, I am a vi apologist. All of this was happening on [ARPANET](https://en.wikipedia.org/wiki/ARPANET). ARPANET - the predecessor to the Internet, was an amazing “new thing”. It had a discussion forum called [Usenet](fhttps://en.wikipedia.org/wiki/Usenet). Usenet had hundreds of newsgroups and it came to play an important part for me in helping to complete my MSEE thesis. 

I posted questions around TCP/IP, coding issues around network drivers etc to the relevant newsgroups like comp.tcpip and the like. I would get replies that worked sometimes, other times got pointed to resources in other sites to explore. These were days of telnet and ftp. The web was still at least 5 years into the future. With help from Usenet newsgroups and various email conversations I was able to wrap up my thesis work. I ended up successfully building a TCP/IP stack on OS/2 - a joint IBM and Microsoft operating system. It only had netbios-based networking native to it (LAN Manager) and not TCP/IP stack. So I thought this was a pretty cool thing to make a TCP/IP working on OS/2. 

In doing all of this, it was very evident to me that sharing all of the work out to the world was the right thing to do. I have [my thesis document](http://tinyurl.com/HarishPillayThesis) that is online, so that's available.

<br/>

**How do you think people can contribute to open source in different ways, whether they are technical or non-technical?**
<br/>

So for non-technical folks, that's what I would encourage them to do. Don't just consume, don't just be a consumer. And within Red Hat, we have an ideal opportunity to be a contributor. It is not just for a technical person who has a technical inclination; it is all of us. If we encounter a problem with the product, we file a bug report. Even that is sufficient. So that's where you can contribute, and we have so many ways. You just need to articulate it. We must demonstrate and explain. We need to explain to people that this is how you can do it and what it means. So I believe that is where I would advise you to begin.

If you are technically inclined, you can get into the weeds of the applications and give feedback. You can file bug reports, and since the code is available to inspect and change, provide code snippets that fix the issues. At the very least, file a bug report with enough information for the developers to get to fixing it.

Find opportunities to showcase open source solutions. For example, if you have Raspberry Pis, run talks and webinars to show how it can be used for all kinds of projects. I'm still figuring out and working on some interesting projects. So for example, because of the lockdown in 2020, I started working on a project which I didn't have time for before. I built a hydroponics system and wired up a bunch of sensors and used a combination of different open source tools to monitor and track the vegetables that could thrive in the system. I am actually quite happy with the system and am now trying to find an even more robust system to increase yields and so on. But the entire system is set up and run with open source software and hardware. 

So I managed to do stuff and write some code, and it worked for me. And then I send a pull request to whoever it was and then see what happens. If they don't accept it, that's okay. It worked for me. So, do you take what you want? Small little actions like that, over a period of time, just accumulate. And by doing it, I think that is when you will feel that you're part of this bigger picture. You are part of the story. As the story evolves, it's an ongoing process. 

<br/>

**How do I get started with contributing your way?**
<br/>

Again, you need to know that this is immensely possible in today's context. You see all those TikTok and YouTube videos where people are creating content on all types of subjects and topics. You could use that to create tutorials, how-tos etc. That is a form of contribution. I think every individual who has an opportunity, whether they are studying history, doing philosophy, or doing electrical engineering, should capitalize on this opportunity to contribute. 

If you are in a university, for example, you have an ideal opportunity to experiment and try out how open source contributions can happen. The challenge, sometimes, is that the faculty might not be cognizant around open source principles of contribution and collaboration. We need to educate the educators on the value of open collaboration. We need to help them understand what this means to the faculty member directly as well as the students who flow through the system. The more empowered both the faculty and students are, the better we will all be as the trained individuals enter the workforce.

Because once they understand it, then they may suggest it to the students. That's one angle. 

We had a program called [POSSE](https://www.redhat.com/en/about/open-source-education/educators) in 2007 or 2008. We ran this program for faculty. POSSE stands for "Professors' Open Source Software Experience." The idea was to bring university professors into a safe space to help them work through on how to collaborate in an open source way. Show them how open source magic happens. Help them learn. Those were the days when IRC was king, and show them how to communicate with somebody in IRC. A lot of them have  never done it before - it was before their time. Bring them, show them the use case, show them a way to collaborate. Sit next to them, and without saying anything verbally, communicate purely via the Internet. Eventually, they get it. When the a-ha moment happens, you will see their eyes light up. 

I had been teaching a class at a local university for about seven years. It was an undergraduate program where I was teaching three-credit classes. And it was all about open technologies, collaboration, and so on. As I was teaching things around open source tech, I was not going to use the school’s content management system which involved both, a restricted access only to registered students etc.

So, I placed [all of the contents](http://ce9005.pbworks.com/w/page/53490854/FrontPage) on a public wiki resource. All of these happened in the days before MOOCs were beginning to happen and the various universities around the world started putting their materials into publicly accessible sites. 

The tools to make things available publicly are trivially available today. It takes a little bit of discipline to get into doing things in the open. You can start by creating and writing blog posts. These posts are primarily for you as a way to document what you do/think about etc. I blog as a means to have a conversation with myself (and also to remind me of tips and tricks of stuff I need to work on). 

<br/>

**Have you ever faced challenges in the open source world?**
<br/>

I think they'll always be challenging. Did I face anything personally? No. The challenge that I think faces everyone, especially with open source contributions, will be burnout. People will be tired. So when I established the [Singapore Linux user group](https://singaporelug.org/) in 1993, a few months before Red Hat itself was established itself, we were running monthly meetings. We did that for many years and it was getting to be exciting times which prompted LUGS to consider, in 1999, to run a conference which we called the  [Singapore Linux Conference](https://www.sixxs.net/archive/docs/ipv6-history/6bone-mailinglist/1998-November/001823.html). We had a lot of people show up. It was in March 1999, and then we ran it in 2002, and yeah, it was just quite interesting. There's a lot of interest in participation. 

While these activities are great to build awareness and interest, it is still a big challenge to get people to volunteer. User groups are driven by volunteers. Sustaining it is NOT an easy task. You need to have succession. You need to have the next generation come in, take it and do whatever it is. Succession is a huge problem no matter where it occurs in any organization including in open-source projects. The Singapore Linux Users’ Group turned out to be a crucible. It started off with the Linux perspective. And then, eventually, so many other things like PHP, Python, Java, various other technologies started becoming interesting which drove interest and the splintering of attention and volunteer time in older groups. These are, in some sense, the price of success and it is fine. 

So you'll find there's a very rich community of contributors in many different areas. But again, it goes back to the same fundamental problem: How do you sustain it? The sustaining part is the biggest challenge. 

Open source groups/projects are not an exception to these challenges. One major benefit of open source projects, when it fails, is that whatever code was cut will always be there for the taking (assuming the right licenses were applied). Someone somewhere will take it and run with it. 

One way to ensure some form of digital posterity is to send the contents - code etc - to archive.org. I do support archive.org through donations and other means so that it continues to exist for as long as possible. That's a part of sustainability that not enough attention is given to. 

<br/>

**Can you recommend any unconventional open source contributors you admire?**
<br/>

You may want to talk to Daniel Veillard while he is in France. He was one of the early contributors to XML. I would suggest that you speak with him because he has his own perspective and I think that these days, driving XML standards has been very critical to many of the things that we see today.
<br/>

Harish, I appreciate you so much for taking the time to share your experience and viewpoint on open source contributions. I have learned lots of things from our conversation, and I hope that it will be helpful to our readers. Thank you so much!

I will leave you all with my favorite takeaway from this interview..

###### It takes a little bit of discipline to get into doing things in the open.


<br/>
<br/>

*Harish has been in the technology industry (Internet, Software, Hardware, Wireless) for about 40 years. He is also a mentor to startups, educator to the next generation of engineers and makers. He has been a board member of international organizations (Internet Society) and also board member of businesses in Singapore and the US. He lives in Singapore with his family. He can be reached out on [LinkedIn](https://www.linkedin.com/in/harishpillay/) or via [Twitter](https://twitter.com/harishpillay).*

<br/>
<br/>

_________________

This blog post is part of the August edition of [UnconventionalContributors](https://www.parthgoswami.com/categories/unconventionalcontributors/), our monthly interview series about different ways to contribute to opensource. If you like this article, check out the [stories of our other contributors](https://www.parthgoswami.com/categories/unconventionalcontributors/) and stay tuned for our upcoming editions.

Have a story to share? We’d be delighted to get in touch and discuss sharing your story. We are also open to suggestions for new content that will foster the community’s growth.

**We’ll see you all in the next one. Till then, Happy contributing!👋🏻**


