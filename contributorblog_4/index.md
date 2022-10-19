# Contributor Blog #4: Interview with Geoff Burke


We have many diverse contributors in opensource that help upstream communities in unconventional ways, which doesn’t require any coding or development skills. Starting with a non-code contribution can help anyone overcome the sense of failure and not being good enough, and it can also serve as a springboard for our open source adventure. This interview series aims to highlight some non-code open source contributions that anyone can make right now to get started contributing.

For this month’s edition, we talked about Ambassadorships, participating in Forums and writing Tech Blogs and  with Geoff Burke.


<br/>

**Thank you for taking some time out and interacting with us, Geoff. Can you introduce yourself and share your journey so far?**
<br/>

My name is Geoff Burke. I've been in I.T for 20 years and I’ve been mainly dealing with data protection for the last 13 years, originally starting with protecting physical machines then virtual machines and recently have started working on containers and Kubernetes.

While exploring Kubernetes, I thought of setting it up over a weekend, but that didn't happen obviously because I had assumed, with all my experience, it would be easy. But it wasn't. I quickly just leveraged Docker Swarm because it was a lot more simple, only to realize that the complexity of kubernetes also created enormous flexibility and enormous capabilities. I ended up doing all the related certification exams [CNA, CKAD, CKA and CKS] which were very difficult and challenging.

<a href="/images/unconventionalcontributors/contributor_4/contributor_4.png" target="_blank"><img src="/images/unconventionalcontributors/contributor_4/contributor_4.png" width="300px" align="right" /></a>


Right now, I’m trying to move my focus totally towards kubernetes which is a bit of a challenge. I also believe this might be a challenge for a lot of people out there, hence, I'm very interested in helping people out because I realize that there are going to be a lot of people who are going to have to take these steps, like I did. Especially those who have already established themselves as virtual machines administrators and now have to make this big change of stepping into container orchestration. 

I have also worked with two major Canadian service providers. One provided backup and data protection and the second one provided an enormous amount of hosting as well, not just in Canada and States, but all over the world. 

I then became a [Calico Ambassador](https://www.tigera.io/blog/introducing-our-exciting-new-ambassador-program-calico-big-cats/) because when I first started working on Kubernetes, [Calico](https://www.tigera.io/project-calico/) was the first CNI I used and ever since then I've never looked back. I remember I had some issues with flannel which got me annoyed and then I just put in Calico and it worked. So that’s where I am at right now.

<br/>

**Was Kubernetes your first experience working with an open source project?**
<br/>

I got introduced to open source products through various linux distros. I started playing around with Linux back in the late 90s. I remember I bought a Red Hat book, can't remember the name, but it was a Red Hat book with a CD. I was in a different location and they had [pulse dial-up](https://en.wikipedia.org/wiki/Pulse_dialing). I was trying to get the modem to dial-up. With Windows it was easy, just click on the next button and you are done. With Linux, it was very difficult, but when it got working I was so happy, plus it was a pulse dial-up. I was also involved with [Slackware](http://www.slackware.com/) and Debian. I've known quite a bit of Linux which helped with kubernetes but it didn't mean it was going to be easy. I've never been a developer so I haven't done any coding, I've done some bash scripting but very minimal, the basic stuff. 

<br/>

**What product(s)have you contributed to?**
<br/>

I am mainly engaged with and contributing to communities more than the product itself. I have been writing lots of posts, beginner posts for people to learn. I also run a YouTube show. [Alara Ozturk](https://www.linkedin.com/in/alara-ozturk-299936106/) from Calico was my recent guest.  Even though I've taken all the exams relevant to my roles, I still consider myself to be in a learning mode because I don't have enough production experience. 

I think the big chunk of learning is the theory, which is covered while preparing for the exams, but then a huge chunk is the experience. Both theory and experience is necessary and if you don't have either, you don't consider yourself an expert. While the Calico ambassadorships are recent and relatively new, I have also participated in IBM’s TSM Fastback forums back then. While doing all of this, I realized that teaching other people also solidifies your own knowledge.


<br/>

**As they say, teaching is learning twice. Moving on ahead, can you describe how your contribution journey started?**
<br/>

I would say that I really followed an example in a sense that, again I'll go back to the late 90s; I was very impressed with all the multitude of Linux. There was Microsoft stuff which was very tight. It wasn't that Microsoft people weren't helping, it's just that in the Linux forums you'd have top experts with no ego who would just help anybody. You could ask a very dumb question and they would just answer it. That always stayed in my mind. 

Later, fast forward to 2013-14, when I started working with RnD forums, I was only watching these forums at first mainly because they were great sources of information. People all over the world might have a problem that you might have a month later so you could see what they did with it. Then I started answering questions myself and I started to realize that it reminded me of the way the Linux users in the late 90s had also helped others out and it became addictive. 

I then saw that Calico was asking for ambassadors. Since I always enjoyed working on Calico, I gave it a try. Another thing that I often stress upon is that while writing blogs, answering questions on forums, or while helping people, you become more solid. Your experience gets wider because people are having problems and are asking questions in different areas which you might not have seen. It's a very fulfilling thing. It is by no means a one-way street. People think that you are contributing all just for free. But you do get a lot in return. It’s subtle, but over a long period of time, you can tell you are growing stronger in your domain, the people around you become stronger and everybody wins at the end of the day. 

<br/>


**Have you ever worked with Calico products before becoming an ambassador?**
<br/>

Calico ambassadors are known as Calico Big Cats. I became the Calico Big Cat in June 2021.  Along with my kubernetes exam preparation, at my present and previous company, I was constantly creating demo setups on kubernetes. Now, the problem here in Canada is that Europe has gone a bit further ahead with kubernetes. North America is moving there but it's a little bit slower. The companies, especially service providers, are worried about missing the Kubernetes bus. 

<a href="/images/ccol1/kubecuddle.png" target="_blank"><img src="/images/ccol1/kubecuddle.png" width="300px" align="right" /></a>


So, I create a lot of test clusters to perform demos and workshops and I always use Calico. I use it because it was easier for me to install, the documentation is clear, and then I  took a couple of free Calico certification exams, which I liked very much. Since I haven’t done much on Azure, I failed 3 times while taking the Azure exam. And that’s what I liked about these certifications. Even though they are open book, they make you prepare and work hard for it. 

I was recently in an AWS Meetup with Alara, in the States (online of course), and while talking about certifications I said that these are challenging certifications. They're open-book but they're not easy and that's good because you don't want something that's just going to be a rubber stamp. I have used Calico a lot. Nowadays, I’m trying to get time to play around ebf dataplane and do the encryption with wire guard. I haven’t used flannel much, Calico is my go-to CNI. 

<br/>

**What would you say about your experience as an ambassador and your contributions to Project Calico now that you have been a Calico Big Cat for more than a year?**
<br/>

One of the things I like about these ambassadorships is that they push you to study a little harder. To give an example, with Calico I immediately hopped on to Udemy and bought three courses because I didn’t know much about the security domain. It puts additional, I don't want to say pressure, responsibility that you have to learn. You don't necessarily need to become a developer or coder but you have to at least have an understanding of the product. 

Throughout the year they'll come up once in a while with offers to participate in events like the AWS Community meeting, CalicoCon where I’m going to try to present a topic, and then there’s this very interview. These events keep you in the loop and ensure that you don’t drift away. Alara will keep coming up with such opportunities. It’s very beneficial and that’s one of the things we talked about with Alara on the community hub show on the Kubernetes corner. Creating a balance for sustainability is important because people have full-time jobs, so you need to ensure they are not overburdened, and also have not become complacent at the same time. 

<br/>

**In what ways have you contributed to Project Calico?**
<br/>

Answering on the forums, trying to help people solve their problems, that was the initial stage of it and it was very basic. Then it moved into feature discussions, in other words ideas we floated about ‘what would you like to see’ and because I was working with the product every day, I started to get actively involved in that and I saw some of the features that I'd asked were actually come to life. I realized that all this is very powerful, so I'm going more in that direction now. I'm actually trying to push my career into that and of course that falls in very well with all these ambassadorships. So it went basically from answering questions on the forums, bigger blog posts on hubs and now it's also gone to speaking. 

I then just for fun created my own little weekly YouTube show too. It's interesting how it went from writing small answers and now it's going into the actual whole audio visual stuff. I now see it going towards teaching possibly. But I wanted to underline that you don't necessarily have to have that personality to get involved in this way because what I saw on the hubs and the blogs is that people have different personality types. Some people are very internal and introverts and yet they produce excellent stuff. 

For instance they do it differently, they're possibly even more detailed, more scientific, more mathematical, a more focused approach. On the other hand I'm more advertising, getting the attention to see the big picture. But there's a place for both. That's the thing with the community. I think it is important to kind of say that it's not just one type. It’s every type just like for any human society you need different people to build this whole structure. Open source communities are no different in that sense, which is a great thing. 

It's been about a year that I am with Calico as an Ambassador. Recently there was this AWS Meetup for a full hour where I gave a presentation about Calico in an AWS Group. I talked mainly about the free certification. When it comes to Calico, they understand  that there's a big learning deficit and there are a lot of people who need to learn about Kubernetes networking and security. So I gave a short description about Calico and what it is, what it does and then discussed the certifications, the pre-certifications. 

I've written blog posts about Calico on the Veeam Hub, and on my own blog as well. Apart from that I have also recorded my video blog that I do every week. I tried to basically keep it relatively simple in a sense because I know that my audience are going to be people who are new. They're not necessarily going to start playing with the eBPF dataplane right away. I can't remember how many but basically whenever I talk about CNI, I focus exclusively on Calico just because I know it better than the other ones. 

<br/>

**That's the definition of being an ambassador. Can you talk about some of the challenges you might have faced?**
<br/>

One of the first challenges, and for anyone who's starting, I'd say is insecurity. If you've been working for a while, you've read other people's stuff and their contributions. It becomes hard to picture yourself doing that and so I think the first few times I started to write some blogs, I was second guessing. I used to say to myself this looks stupid or this is dumb or maybe I've made a mistake and someone's gonna call me out on it. You have to overcome that fear and once you overcome that fear then you just have to make sure you remain disciplined and don't become lazy or sloppy. And that's why it helps to be in these communities too. You see other ambassadors and contributors and realize everyone's human. People make mistakes and it really comes down to how you respond to that. Having said that, I'm very careful with what I am doing. I don't go outside of my lane and stay within what I know and then try to double check. 

Another challenge is the time bounce. So first of all you have to be with an employer who understands that contributing is important for you and that this is not after hours fun. With family and kids around, you have to be able to do some of this at least during the day and during working hours. If you can't then it's then going to tire you down. You could get sick of it at some point. You'll say why am I doing this, I will simply get my paycheck and work nine to five at the minimal level. Hence, you want to ensure that it doesn't kill your enthusiasm. That’s the second big challenge. 

You need appropriate time for your contributions so that you know what is going to be for the evangelist stuff, for the ambassador stuff. You have to be able to organize and you have to make sure you're involved

<br/>

**Share your experience in becoming a contributor.**
<br/>

I think contributing brings more structure. I started by participating in the forums, by answering the questions, then I started with blogs and vlogs. I participated in the forums which was much more from a selfish point of view. At first, for any problem or error, I used to look for help and go to support. But support takes a long time and hence I got into the forums. Then I started to answer things and it became a bit addictive. Having a contributor title means that you accept that as responsibility. You take pride in having it but that also adds a certain amount of self-discipline. You realize you need to do something to keep contributing, but it’s not a pressure. 

Thinking about having the title makes you happy every time if you're having a bad day. It's one of those little pleasant things that just sits there. This is where the talk with Alara can be really interesting. It's very important that the person from the other side, the organizer of the community, does a very good job because it's difficult if you're dealing with a bunch of human beings coming from different cultures, often from all sorts of countries, having different ways of doing things. How do you organize such a community? How do you make them work effectively, not as a team because we don't really know each other. If you don't have someone who's doing a good job organizing it, then it kind of rubs off. The groups I've been in, all have very competent and capable people. 


<br/>

**Recommend one unconventional contributor whom you admire and tell us more about them.**
<br/>

Michael Cade is someone I have enormous respect for. He produced a  blog series this year titled ‘90 days of Devops’ which has gained a lot of attention. Michael also comes from the data protection world and was firmly settled in Virtualization but has made an astounding journey into DevOps.

I had read about Michael before because he was big in the VM world and he was an excellent contributor. I came in contact with him and was shocked to see that he had no background in kubernetes and in a year he was able to produce the [90 days of devops](). Now, his job was not to become an expert in CNI or in CSI storage, his job was at the evangelist level, to get an understanding about the subject and to be able to produce something. People who were in the devops world read the content and found it excellent. He was not going deep, he was shallow but he was going into every important area just enough and he got on the list of most important people like [Kesley Hightower](https://twitter.com/kelseyhightower). I also found it impressive that he has no ego, he doesn't show off. He is just one that I know very well so it is easy for me to talk about some aspects of his work and personality that I found to be something I try to follow.

<br/>

**Any word of advice for the upcoming Calico Big Cats? In what ways can they contribute?**
<br/>

I think one thing they could do is to work closely with Alara because she sees the full picture of what everyone's doing. And again going back to what I said before, there are people with different skill sets, different roles, different abilities and so she can help the new ambassadors if they're not sure of what to do. Apart from that, again I go back to saying try to learn the product more because it's important. It doesn't mean that you have to go out and do an expert talk. Remember we're not replacing sales engineers at Calico. They are the people who are in direct contact with developers, they have all the secrets. Our job is to share what we know in our communities and our connections to spread the word. So I think that the big thing is to find something you're comfortable with, discuss it with Alara and then just go forward and have fun. 

![](/images/ccol1/bigcat.png)


<br/>

Geoff, I appreciate you so much for taking the time to share your experience and viewpoint on open source contributions. I have learned lots of things from our conversation, and I hope that it will be helpful to our readers. Thank you so much!

I will leave you all with my favorite takeaway from this interview..

###### You need appropriate time for your contributions so that you know what is going to be for the evangelist stuff, for the ambassador stuff. You have to be able to organize and you have to make sure you're involved.


<br/>
<br/>

*Geoff Burke is a Senior Cloud Solutions Architect at Tsunati with over 20 years of experience in IT and 13 years working with Data Protection. He has worked with top Canadian Service Providers leveraging Veeam Cloud Connect. Recently he has been become intensely focused on Kubernetes. Certifications include VMCA2022 VMCE2021, KCNA, CKS, CKAD, CKA. In his spare time, he likes to spend time with family, cycle, camp, see films, and watch documentaries. He also spends a lot of his free time in learning technology. He can be reached out on [LinkedIn](https://www.linkedin.com/in/geoff-burke-0a174684/), [Twitter](https://twitter.com/CloudRestore) or via [email](https://mail.google.com/mail/u/0/?fs=1&tf=cm&source=mailto&to=geoff.burke@tsunati.com)*

<br/>
<br/>

_________________

This blog post is part of the Sept edition of [UnconventionalContributors](https://www.parthgoswami.com/categories/unconventionalcontributors/), our monthly interview series about different ways to contribute to opensource. If you like this article, check out the [stories of our other contributors](https://www.parthgoswami.com/categories/unconventionalcontributors/) and stay tuned for our upcoming editions.

Have a story to share? We’d be delighted to get in touch and discuss sharing your story. We are also open to suggestions for new content that will foster the community’s growth.

**We’ll see you all in the next one. Till then, Happy contributing!👋🏻**


