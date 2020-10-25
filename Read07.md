# APIs continued

## What Google Learned About Teams

 Julia Rozovsky

![ex](Read07-j.png)

25-year-olds who wasn’t sure what she wanted to do with her life
in 2009, she chose the path that allowed her to put off making a decision: She applied to business schools and was accepted by the Yale School of Management.
she was assigned to a study group carefully engineered by the school to foster tight bonds.

![ex](Read07-1.png)

Every day, between classes or after dinner, Rozovsky and her four teammates gathered to discuss homework assignments, compare spreadsheets and strategize for exams.

These shared experiences, Rozovsky hoped, would make it easy for them to work well together.
But it didn’t turn out that way. ‘‘There are lots of people who say some of their best business-school friends come from their study groups,’’ Rozovsky told me. ‘‘It wasn’t like that for me.’’

> Instead, Rozovsky’s study group was a source of stress. ‘‘I always felt like I had to prove myself,’’ she said.

So Rozovsky started looking for other groups she could join.
A classmate mentioned that some students were putting together teams
for ‘‘case competitions contests’’  in which participants proposed solutions to real-world business problems
that were evaluated by judges who awarded trophies and cash.

The members of her case-competition team had a variety of professional experiences:
Army officer, researcher at a think tank, director of a health-education nonprofit organization and consultant to a refugee program.
Despite their disparate backgrounds, however, everyone clicked.
They emailed one another dumb jokes and usually spent the first 10 minutes of each meeting chatting.
When it came time to brainstorm, ‘‘we had lots of crazy ideas,’’ Rozovsky said

**Rozovsky told me. ‘‘No one worried that the rest of the team was judging them.’’ Eventually, the team settled on a plan for a micro­gym with a handful of exercise classes and a few weight machines. They won the competition.**

> **some people are so much more effective than everyone else.**

Yet many of today’s most valuable firms have come to realize that analyzing and improving individual workers ­— a practice known as ‘‘employee performance optimization’’ — isn’t enough.

In Silicon Valley, software engineers are encouraged to work together, in part because studies show that groups tend to innovate faster, see mistakes more quickly and find better solutions to problems. Studies also show that people working in teams tend to achieve better results and report higher job satisfaction.


Five years ago, Google — one of the most public proselytizers of how studying workers can transform productivity — became focused on building the perfect team. In the last decade, the tech giant has spent untold millions of dollars measuring nearly every aspect of its employees’ lives. Google’s People Operations department has scrutinized everything from how frequently particular people eat together (the most productive employees tend to build larger networks by rotating dining companions) to which traits the best managers share (unsurprisingly, good communication and avoiding micromanaging is critical; more shocking, this was news to many Google managers).

![ex](Read07-2.jpg)


Some groups that were ranked among Google’s most effective teams, for instance, were composed of friends who socialized outside work. Others were made up of people who were basically strangers away from the conference room. Some groups sought strong managers. Others preferred a less hierarchical structure. Most confounding of all, two teams might have nearly identical makeups, with overlapping memberships, but radically different levels of effectiveness. ‘‘At Google, we’re good at finding patterns,’’ Dubey said. ‘‘There weren’t strong patterns here.’’

![ex](Read07-5.png)

After looking at over a hundred groups for more than a year, Project Aristotle researchers concluded that understanding and influencing group norms were the keys to improving Google’s teams. But Rozovsky, now a lead researcher, needed to figure out which norms mattered most. Google’s research had identified dozens of behaviors that seemed important, except that sometimes the norms of one effective team contrasted sharply with those of another equally successful group.

The researchers eventually concluded that what distinguished the ‘‘good’’ teams from the dysfunctional groups was how teammates treated one another. The right norms, in other words, could raise a group’s collective intelligence, whereas the wrong norms could hobble a team, even if, individually, all the members were exceptionally bright.

![ex](Read07-3.jpg)


if you are given a choice between the serious-minded Team A or the free-flowing Team B, you should probably opt for Team B. Team A may be filled with smart people, all optimized for peak individual efficiency. But the group’s norms discourage equal speaking; there are few exchanges of the kind of personal information that lets teammates pick up on what people are feeling or leaving unsaid.


 In late 2014, Rozovsky and her fellow Project Aristotle number-crunchers began sharing their findings with select groups of Google’s 51,000 employees. By then, they had been collecting surveys, conducting interviews and analyzing statistics for almost three years. They hadn’t yet figured out how to make psychological safety easy, but they hoped that publicizing their research within Google would prompt employees to come up with some ideas of their own.

![ex](Read07-4.jpg)


# Who is “Roy Fielding”

He helped write the first web servers, that sent documents across the Internet.

and then he did a ton of research explaining why the web works the way it does.

His name is on the specification for the protocol that is used to get pages from servers to your browser.

## What the HTTP Do

tells the browser what protocol to use.
That stuff you type in there is one of the most important breakthroughs in the history of computing.

## What the URL Do

URLs tell the browser that there's a concept somewhere.
A browser can then go ask for a specific representation of the concept.
Specifically, the browser asks for the web page representation of the concept.

## Why can't a machine understand a normal web page

web pages are designed to be understood by people. A machine doesn't care about layout and styling.
Machines basically just need the data.
Ideally, every URL would have a human readable and a machine readable representation.
When a machine GETs the resource, it will ask for the machine readable one.
When a browser GETs a resource for a human, it will ask for the human readable one.

More or less, this is what engineers do in the web development world,
thanks almost entirely to the popularity of RESTful web frameworks like Ruby on Rails.

> But this is a very recent change! Just a few years ago, the large majority of developers were busy writing layers of complex specifications for how to access data in a different way that isn't nearly as useful or eloquent. Nouns weren't universal and verbs weren't polymorphic. They basically ignored throwing out decades of real field usage and proven technique and kept starting over with something that looks a lot like other systems that have failed in the past. They used HTTP but only because it let them talk to our network and security people less. It was like trading simplicity for flashy tools and wizards.

