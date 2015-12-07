# Leading change in organizations of all sizes

## Some context

This post is about bringing change to an organization — something hopefully all of us do in our careers at some point. Depending on the organization you are in, you may be led to believe change can only be brought about by management, but I don't believe this is true. This post talks about bringing change mostly from the perspective of an Individual Contributor (IC), because that is usually the least privileged source of change. If you are reading this from a position of leadership in your company, consider whether your organization is structured to enable individual contributors to use these sorts of techniques.

Okay, so you're ready to make some awesome change! There are a few guidelines:
* Change is hard, don't be a jerk about it (tip-o-the-hat to Jeff Hackert).
* When you seek to improve something, you may imply the current thing isn't good enough. [Be sensitive](http://www.retrospectives.com/pages/retroPrimeDirective.html) to those who put the present thing in place. 
* Be aware of how your changes could shift power away from people who presently have influence (or be interpreted as doing so). People don't generally enjoy losing influence.
* Change is hard, and it takes time. Be patient with yourself and others.

> A number of years ago I participated in a team who brought continuous deployment to an organization for the first time. That team later worked to reproduce their work using Chef, so that other teams could build on our success. That experience involved all of the steps in this blog post. At each stage in this process I’ll try to talk a little bit about that real world experience and how each stage occurred. 

## Why change sometimes doesn't work

We should get his out of the way up front — sometimes this just doesn't work.

Many of us have stories of trying to change something about where we work, and becoming frustrated after putting in a lot of work for little or no impact. This happens for all kinds of reasons, but usually comes down to one thing: unmet prerequisites. These are not necessarily requirements of your specific change, but they need to be in place before your change can happen. An example is trying to introduce refrigerators into a building with unreliable electric power. It doesn't matter how compelling your argument for refrigeration is, if the power isn't reliable then refrigeration will not keep things consistently cold and food will spoil. The power reliability must be addressed first, and then refrigeration can follow. 

Unreliable power can be replaced with "unreasonable management,” "unreliable software testing,” "unexpected regulatory constraints,” etc. Some of those things will be in your power to change, some of them will not.

[Conway's Law](https://en.wikipedia.org/wiki/Conway%27s_law) also applies here. Your organizational structure will probably only support certain models for communication and management. This can place surprising limitations on what types of change your organization is capable of adopting. 

A siloed organization with a top-down communication structure may struggle to adopt cross-functional team approaches and technology that benefits from those structures. Similarly, technical changes which reduce the control individual teams have over their infrastructure may not allow existing cross-functional teams to operate their services. If you are introducing significant changes to an organization like this, look to first implement changes in a small group within the larger organization. Communication structures in a small group can more easily shift to support the desired communication patterns. 

## Beginning change: The seed of an idea

*"The impediment to action advances action. What stands in the way becomes the way."* - Marcus Aurelius

> The problem for our team was that we needed to build a new service, and the tools available to deploy that service weren’t great. I recall the day we had standup, and our lead announced we were building this new service. Someone asked, “Can we try using continuous deployment?” We had a cross functional team (Dev, Ops, Build & Release, Testers), and after some discussion everyone was willing to give it a try. So we did. 

> After the initial success of continuous deployment we wanted to expand the idea to other teams. We had to start over here again, taking the lessons we learned and applying them to new teams.

Change usually starts with a problem. When you realize this obstacle is something that may stand in the way of others, then you've found an opportunity for change. Now, if the problem only impacted you, then you just fix it and move on. That was boring, wasn't it? The hard, complex part about change is that it impacts others. Most of your work enacting change is focused on others — learning their perspective, communicating, collaborating, and more. 

Sometimes your idea is an obvious improvement to a situation many folks are experiencing. Other times your idea is pretty experimental, and you need to spend some time proving to yourself (and eventually others) that it can work. Either way, it's imperative you get some feedback on your idea.

The least costly way to get feedback is to ask for it. (I know, crazy right?) Both asking for and responding to feedback are skills that take practice. If you ask the wrong questions, or don't know how to probe for more information, you might not get useful responses. Ask anyways. You should start with people you trust and work your way toward people who would be impacted by your change. This asking can be challenging, so read on. 

## Understanding others' view of the problem

> We decided that we wanted to continuously deploy our service, but what impact would that have on the rest of the organization? Would the time and effort involved in building a new way of deploying services actually be beneficial to the organization? We started by talking to other Leads & Architects in the organization about whether continuous deployment was a reasonable step forward for other teams. In comparison to our monolithic app which shipped every week, the idea of deploying changes in minutes was exciting to some and terrifying to others. The general sentiment though, was that it was a worthwhile experiment and that, if it worked, the gains would be significant. 

When we have an idea about how to change the world, we want to share our idea with everyone. The problem at this stage is that our idea of the solution might not be quite what the world needs. We need to start by understanding other views of the problem. We need to understand enough about how others view this obstacle and what their constraints are to be able to see how our change might improve their lives without making things worse. Critically, we need to understand if others even see the same problem we do.

### How to get more information

When I need to learn about how someone else views a problem, I sweep my idea off the table for the time being and focus entirely on them and their needs. At this stage I'm not trying to convince someone my idea is good — I don't know if it is — I'm trying to gather information. A great way to approach this is to just setup a 1:1 with someone who understands what is currently in place and ask them, "Can you give me some history on the way we do this?" If asked why, you should be honest: "I want to make sure I understand the context for this situation." If you find the right people, you will probably learn more than you ever expected about how things became the way they are. 

Next, you want to understand folks view of the problem you are trying to solve. Again, I ask open-ended questions. I describe what I understand as the present situation and ask them, "If you could change this to be more ideal, what would that look like?" You can ask this question of the same person who gave you a brief history of the world, you could also go off and find someone you think considers the current situation a problem. Just beware of [confirmation bias](https://en.wikipedia.org/wiki/Confirmation_bias) and seek out folks who are likely to disagree with your idea as much (or more) as those who would agree. 

Side note: The larger the company, the more distributed details will be about how things got to their current state. Seek out folks who have been at the company a while, set up 1:1's with them, and just let them talk about these topics. Take detailed notes, and ask if you can follow up if you have more questions. Very often, management folks know exactly who these people are and can point you in the direction of knowledgeable people on a given topic. Managers are also familiar with what other groups might be good sources of additional feedback.

## The prototype

> The first versions of our service were exceptionally basic. We knew that if we made continuous deployment work up front then we could more rapidly iterate on our service and learn faster. We prioritized all our initial effort around building a deployment pipeline and monitoring that was fully automated. Once those things were in place, we could experiment very rapidly with code changes both in test and in production. As the capabilities of the service were expanded, production data was pushed into the service to allow even greater learning about how the service would behave once it was in production.

> Similarly, when it came time to build this process using Chef, we selected services we owned as a team to experiment with at first. Each time we expanded support to something new, we made every effort to prioritize learning over all else.

Once you feel like you understand the problem from several perspectives, and have refined your idea for a solution, then it's time to build a prototype. The prototype has one simple purpose: to allow you to learn. A prototype should be scrappy and fast while maximizing learning about potential solutions. [Tom Chi's talk about google glass prototyping](https://www.youtube.com/watch?v=d5_h1VuwD6g) gives a great view of how much you can learn from scrappy prototypes. 

When we think about prototypes, we usually think about an application or a physical thing we build, but prototypes also apply to processes. It isn't that much different, except that sometimes it's harder to use a process in isolation to learn. You may need to get permission to experiment with a new process in an isolated group or project. The same expectations apply: You need to structure your experiments to maximize learning and be willing to adjust your prototype as you learn more. If you are working with a group, they have to be willing to do it too. 

As you learn, iterate your prototype toward a version of your solution that someone can actually adopt. This means iterating towards a version that displays the value of your solution to others. Don't focus on the technical merit of your solution. Elegance is nice, but actually adding value in your audience's daily work is what will get traction and allow your work to continue. 

## The early adopters

*"It's amazing what you can accomplish if you do not care who gets credit."* - Harry S. Truman

> During the first implementation of continuous deployment, no one was using it outside of our team. We were building our prototype. As we expanded support however, we needed to prove that we had a solution that other teams could use. This meant finding a team who was both interested in continuous deployment and tolerant of problems. There was enormous interest from teams who wanted to be the first to adopt this new tooling — but there were far fewer teams who could afford the impact to their availability and delivery timelines that could result from being early adopters. 

In most companies there are individuals or groups who are more willing to work through bumps in the name of progress. These folks are often already on the leading edge of change in the organization, and are often already working on experimental projects. These are the first people to talk to about leveraging your prototype. For this conversation, you should start back at the "understanding others’ view of the problem" section to evaluate if they are a reasonable fit for your project. If you find that they are, your next role is to support them as fully as you possibly can. 

That Truman quote comes to life here. You will take all the responsibility for failures that happen around your new idea and you will give your early adopters all the credit for every success. They are putting their own project at risk to allow you to learn and be successful and they are relying on you to support them. Believe me, the people who matter will know your role in a successful outcome. But also know that no success is possible without your early adopters, and absorbing the impact of problems while directing all the success toward them will give you a longer runway to make your solution work. You want to maximize that runway.

As you work through improvements with your early adopters, focus on the **value** of every effort you make. Be critical of changes that don't lead to more learning or don't deliver real and immediate value. There will be a lot of tendency to think about how a solution impacts the next person who tries to implement this. Resist the urge to address those concerns unless it adds value now. In many cases, this is premature optimization that could lead to complexity without value. Remember, focus 100% on your present early adopters. 

## Tell a story

> The first version of our new service simply responded with “Hello World!” to all requests. When we provided a demo of our Hello World app, we deployed it to production. The new service wasn’t very interesting to anyone, but the idea that you could make a change that went all the way to production during a 5-minute demo was valuable. We tied together two demos to share this idea: one showing the deployment, and one showing how the deployment triggers dynamic changes to the metrics we were monitoring. The story we were telling was about how rapidly you could turn changes to your application into feedback in production. This story guided future demos, and effectively communicated the tremendous potential of continuous deployment. 

It is so easy to stay heads down and focused on your problem and your awesome solution — but being able to share why, how, and what you're changing can help others see your solution as an opportunity for them. As we mentioned at the beginning of this post, this effort is focused on the needs of others, and telling your story is an important part of showing others how you can help.

### How to tell your story

**Share your progress as often as possible**. Many companies have engineering forums, like end-of-sprint demos, for sharing your progress.. Share in the context of this being a work in progress, focus on the value you are bringing to your early adopters, give them as as much credit as you can for the progress that has been made and how they've helped you work through problems.

**Write a blog post about your experiences**. What have you learned? What didn't work? What did work? What do you think is coming up next? Your personal or company blog might be the place for this, but if the change isn't something you can talk about publicly, write something up internally. Many companies have a wiki that supports blog posts or an internal blog. 

**Go talk about it at a conference or a local meetup**. Whether this change is a significant shift in the way your company works, or a relatively minor but important course correction, people in other organizations will be interested to learn how you did it. Keep telling the story over and over as long as it's worth telling. As you tell the story, it'll evolve and you will get new feedback about what the next evolution of the idea could be.

As you get feedback, listen for your next early adopter. Who sounds interested? Who has a problem that could teach you more to make things even better?

## Expand support and mature the idea

> The first implementation of continuous deployment took about three months to complete, and the service that leveraged it took another six months before it was in production. Over those nine months, we gathered significant data that showed that continuous deployment worked, and enabled development teams to move faster. A number of other teams were interested in doing the same thing, but the organization didn’t want everyone to invent their own way. The tools that worked for the first service should be augmented to support additional services. 

> A team was formed, composed mostly of individuals who participated in the first implementation, to find a way to build a reusable framework for deployments. This didn’t happen on its own. It was a result of members of that original team telling stories, talking to other teams about how they could benefit from continuous deployment, and considering ways support could be expanded to better support the organization. 

Depending on the change you are trying to make, you may have found others who are interested in taking on the primary responsibility of pushing it forward. In larger organizations, with more formal responsibility structures, this will probably not be the case. You'll need to continue evolving the solution. This cycle starts again at understanding the needs of your next early adopters, extending your prototype to support them, and then sharing your progress and incorporating feedback. 

As you get attention and traction on your idea, you are likely to get questions. This may be a few, informal questions here and there, or you might get notes from architects and leaders who realize the impact of the change. Some of these conversations might sound like they are calling your work into question — "Why are you doing this?" There's a strong tendency in these conversations to be defensive, but try very hard to see these conversations as opportunities to build support. It's worth spending a little time preparing for these conversations in advance.

Some suggestions to think about:
* You haven't yet proven your idea can work broadly in the organization. Be honest about what you’ve done, the benefits you’ve observed, and why you think it might work beyond your early adopters. 
* What are some obstacles you can see ahead? Who could help you work through those?
* What is a realistic long-term view of the value of this effort to the organization? Think about this from both a technical and non-technical perspective if this is a technical change. I like to ask "How will this benefit customers?"
* Who's [agency](https://en.wikipedia.org/wiki/Agency_%28philosophy%29) is impacted by this change? Who is going to be threatened by a loss of influence? Have you talked to them?
* Remember that company employees can be customers, too. Their time and happiness has value.
* How are you going to step away from supporting this solution in the future? How does this gain a life of its own?

If your first early adopters are successful there's a good chance you'll be asked to repeat that success. You need to be able to step away from this instance of change, and allow others to stand on the base you've built to evolve it in their own way. This allows the solution to evolve in a way that the organization can support long-term, but it also allows you to move on to something new. If you've built a team around bringing this change to the organization it's time to start thinking about how that team disbands. If that team *is* the change you've brought, then you need to think about how you rotate folks in and out of the team. 

The organization must be able to own this new way of doing things, just as it owns any other business unit, team, process, or tool. This process may take years, and the longer it takes, the harder it becomes. The problems created by not doing this are often visible in organizations where an individual or small group is overwhelmed supporting some pivotal piece of the system without adequate organizational support. The, “If it works, why fix it?” mentality persists largely at the expense of the individuals, and often leads to burnout. 

## Moving on and making more awesome

I wish I could write a story about how our new and expanded continuous deployment implementation was wonderful and everyone adopted it, but that isn’t what happened. What happened was that the second team (and then eventually a third team) used our new version of deployment, and found it to be a dramatic decrease in efficiency compared to the original implementation. Further, the implementation required constant support, the learning curve was steep, and it was much more entwined with the development process so problems became development blockers. The reality began to creep in that it was going to be very difficult for our team to allow other teams to fully own their own deployments with this model. 

Ultimately, that second iteration turned into a third iteration, and eventually a fourth iteration. Each time, remaining mostly constrained to those early adopters as the teams worked to find a solution that would extend to the broader organization. The original team who implemented this was disbanded to work on other projects, and teams who were early adopters were left with very little support. This is not the ending you want. 

In [Jesse Robbins' 2012 Velocity talk](https://www.youtube.com/watch?v=OU8ihx3nT6I), he says, "Don't fight stupid, make more awesome." I always want to be making more awesome. There's a careful balance between abandoning a project before it has legs of its own, and staying engaged for too long and allowing the organization to avoid supporting the idea on its own. As you move through your career making awesome changes, you will learn how to feel your way through this balance. Hopefully this post provides some insight into what that balance looks like to me today, but realize I'm also constantly learning and hopefully improving. 

This journey is different for everyone and, for me at least, it's all about the story. So go forth and make more awesome stories!

## References and Recommended Reading / Viewing

* [Exploiting Conway's Law for Underpants and Profit](https://vimeo.com/65552395) - [Jeff Hackert](https://twitter.com/jchackert) talks about creating change without being a jerk. Watching this multiple times might be required, but there are so many important messages in here about making change in an organization. It's also fun. 
* [The Phoenix Project](http://itrevolution.com/books/phoenix-project-devops-book/) - [Gene Kim](https://twitter.com/RealGeneKim) tells a fantastic story about applying broad change to an organization by focusing on value and experimentation
* [The Tipping Point](https://en.wikipedia.org/wiki/The_Tipping_Point) - Malcolm Gladwell describes in great detail the various stages of an idea as it gains traction
* [How Great Leaders Inspire Action](https://www.ted.com/talks/simon_sinek_how_great_leaders_inspire_action?language=en) (video) - Simon Sinek talks about how to inspire action in others
* [Changing Culture & Being a force for awesome](https://www.youtube.com/watch?v=OU8ihx3nT6I) - Jesse Robbins talks about culture change & his experiences in making awesome
