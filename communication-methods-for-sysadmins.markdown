Communicate ALL the things in ALL the places
--------------------------
"Where is that documented?" or "Was there an email about that?" are pretty
common things to hear around most technical organizations. I cannot count the
number of long-winded email messages I've sent out describing every detail of
an upcoming change, only to have someone ask me "What are you doing?" when I
execute the change. 

Whether we like it or not, we are all about "me". When someone else sends an
email about something, our interest in that thing is inversely proportional to
the length of the email. When stuff breaks at 3am and we *know* there was an
email sent out about that - we go looking and can't find it - so we call the
person who sent it. They are now ecstatic they invested 1/2 a day crafting
that email. 

This post is about communication & documentation for day to day stuff. This is
not the documentation you dig through when you have all day to sort out a
problem. This is the stuff you want now. 

Pop the hood on any car and you'll see an example of this documentation,
right there, all the stuff you are most likely to care about when you are
looking under the hood. It doesn't matter if you've ever driven this car or
not - the documentation is placed as close to the problem as it can get. 

# First - lets tackle email
I know, **gasp**, email for communication? It's a fact, so here are some ways
to make it suck less:
* Questions or conclusions at the top. If you have a short version of the
  email, put that at the top. If you have a question you care about it belongs
  at the top.


*Create a change log*
It's not perfect and it probably will not get used all the time, but it's a
place where folks can document stuff they change in detail. There are all
kinds of ways to implement this:
- A wiki page
- A blog (each change is a new post)
- A git repo (markdown docs for details, git log for timestamps)

Whatever it is, make it *easy* and *accessible*. If you want people to update
it then it has to work into their workflow. The lowest common denominator is
usually a text editor and a web browser.

*Link documents to other documents*

