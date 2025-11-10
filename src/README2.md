# Introduction

Technology promised to make our lives better. Then something odd happened —
people quickly discounted the value that it brought. Instead, we focused on the
friction it added. We're biased towards paying attention to failures. People pay
attention to those failures — and if we build technology products, of course we
should too.

But… at the same time, some technology just works, it's quitely sucessful,
boring even — remarkable because it's never remarked on. The product itself may
gain glowing reviews and fantastic outcomes, but the technology —
it's boringly unobvious, friction-free, success-prone.

## Why You Should Read This Book
How do you create such unremarkable technology? That's the answer we will provide.
You have a remarkable product idea, you want to deliver fantastic experiences to
your users, and you want to ensure that your technology does not become the
negative talking point of your product — this is the book for you.

## About the author
I've worked in technology for 30+ years, and built many systems.
I've made many mistakes, and experienced significant technology waves
(mainframe, client/server, internet, cloud, mobile, ai).

I co-authored the AWS Well-Architected Framework. I led the AWS Well-Architected (WA)
team, which was responsible for answering the question from the CEO of AWS:
"How do we help our customers be well-architected?".
I've patented methods for reviewing architectures, and created an AWS Service,
from inception to GA, leading to improvements in customers architectures at scale.

Through AWS Well-Architected, tens of thousands of customer's architectures have 
been reviewed, and improved. Our answer to the original question showed that a 
magnitude more issues were recognized and addressed by customers, than would happen organically.

However, since leaving AWS I used the time to think about what WA got right,
and what it got wrong. I've watched as other vendors create their own frameworks,
and Gartner even adopt it as a way to measure vendor capability.

Since AWS I have worked in publishing, finance, ai/robotics and have
continued to think about 
better way, lessons learned, hindsight etc

# What we learned
Since building the WA Framework, we learned
* Pillars are a great idea for authoring at the start, but most topics span any
pillar system. For example ensuring a system is available is both a reliability and
a security topic. A better approach would be to not place topics into pillars, but
instead tag them. This way authors know to cover both aspects, and users of the
framework don't experience repetition.
* People perceived any vendor authored framework as being biased to selling that
vendors product. Even when the original authors explicitly wanted to avoid that.
* We purposefullly avoided certain pillars, focusing first on what mattered to
improve customer outcomes. In any revision we need to consider at least (some could be merged)
  * Business (org, growth, governance)
  * Product (work backwards, continuous mindset, fitness function, boostrap iterations)
  * User Experience (papercuts, dependencies)
  * Developers Experience (platform, waste, progress)
  * Ethics (future, ),
  * AI (data, ground truth, )
* Lens were a great way to handle issues specific to an industry or type of workload.
* Green-washing was not helpful. AWS added "sustainability", which frankly would
have been better covered with tweaks across Performance/Cost and a Lens. 
* We should have prioritised open source data gathering, allow all to learn
from each others failures. This would also remove the bias towards "opinion" that
all authors suffered from, or at least made it more transparent and data driven.
* There are two spectrums that mean we need to think about 1} different ways of working
2} governance 3} coordination
  * Single person startup -> Large Enterprise
  * Invention -> Commodity
## industry
* The industry Cargo-Cults at a far faster rate than expected, turning something
that was meant to be a considered useful review into a checkbox exercise.
  * a great example of this is DevOps, where rather than focusing on individuals
  having both dev and operations skills, we ended up with a noun (a role), 
  as opposed to a verb (an action).
* Vested interest will try to complicate any method so they can sell consultancy
and tooling. Whilst consultancy and tooling should be a good thing, it should not
be at the expense of undermining the original purpose.
  * a great example of this is Scrum, where rather than focusing on individuals
  delivering value to customers, it focuses on managing the work.


# History
Working in technology for 30+ years, I built lots of clever and cool code.
I architected complex distributed systems, modelled complex behavioural data,
content systems, multi-platform, global, secure, compliant... and I made
many many mistakes: focusing on the technology instead of the product; not
thinking about "How will we operate this thing"; using too many tools; not
using enough. Following fads, not following them. Deleting the wrong thing
in the wrong environment etc.

Along the way I got promoted into "Architect", a phrase that means
"This person has made lots of stupid mistakes, so they might spot yours".
I got to review other people's systems, and try and avoid the business or
technical mistakes. In 2010 I created a way to understand a teams use of 
best practice "The Pragmatic Capability Model Of Software Delivery (PCM-OSD)"[^1].
I wanted to answer “How good are we at delivering software products?”,
which required being able to measure "quality", which in turn leads you
to wanting to know what even "good quality" in technology building was.
It was an unholy attempt to combine measurements of Agile/Scrum/DevOps/CMMI.

It kind of worked, we could recognise the teams from the results, and
where any opportunities for improvement where. The Captain Obvious
takeaway was that introducing best practices at the start was a lot
easier that adding afterwards — so measure to understand where
teams need more training/enablement for *future* work.

I then joined AWS in 2011 as a "Solutions Architect", helping customers
understand how to move from "on-premises" to the "cloud". I spent years
reviewing "architectures", thousands of them — helping customers make
the changes needed to take advantage of the vendor's platform.
Along the way I was also trying to work out why some worked well,
and some did'nt. Understanding cultures of "high-performing" teams,
seeing success where every "best-practice" was violated. And the same
mistakes[^2] made so many times
("I thought you backed up the server",
"What do mean no one printed out the recovery plan",
"I thought the certificate would refresh itself").

And then in 2012, AWS had one too many "large scale event" LSE[^3], where some
AWS service did what systems do  — broke. Unfortunately, customer's
systems went down hard as well.

*"This has made a lot of people very angry and has been widely regarded as a bad move."*[^4]

In the post-mortem of these events, AWS learned to improve their systems, but
they also discovered something concerning. AWS had provided primitives that
customers could use to handle failures… but people being people, they had not used
them — they had not followed "best-practice". The CEO[^5] was unhappy about this,
and asked the question "How do we help our customers be well-architected?".

This question ultimately landed on the amazing Erin Rifkin's door-desk[^6] as the
"Well-Architected Initiative". This led to a Kaizen to
work out how to improve this situation, and I was the European representative
sent to Seattle to take part. This was AWS at its best, a small number of
people focused on solving the customer problem, with zero limitations, but
an absolute need to deliver something, to start iterating.

We started listing the reasons why customer's systems failed, trying
to find the common patterns of failure. Each person in the room
had their specialist skills, so tended to be pulled into customers
with problems in that specialist area. I suggested[^7] that we use
"ISO/IEC 25010:2011"[^8] product quality model to group issues: "Security",
"Reliability", "Performance Efficiency" etc. This led us to the idea
of that Solutions Architects (SA) should check for these issues when talking
to customers, do a "Well-Architected Review".

We had limited resources so we would start with the biggest/visible customers
first. We would keep track of which ones had been reviewed, and get SAs
to work work through the list in their geography. About this time a
spreadsheet was created[^9] that had all the issues to ask about  — 
SAs could fill it in per customer to record that outcome.

2012: Inception
2013: |______________kaizens, SA reviews, internal SA tool, what else?
2014: |
2015: Erin & Fitz create WA team, Whitepaper published (oct re:invent)
2016: Operational Exc. pillar
2017: Lenses
2018: Self-service tool
2019: global availability

AWS continued to have LSEs, but now the attention became on if
the customers impacted were Well-Architected or not. It became clear
that just reviewing architectures with customers was not enough, we
needed to educate our customers. We decided we needed to write a
white-paper to capture what "Well-Architected" meant, we wanted something
that was scalable. Each of the original main contributors in the Kaizen
was asked to write about their area, I owned "performance" and managed
to finish my draft first. I had stumbled on the idea that we would
cover the topics in the area as a question, as that worked well. 
At this point it was clear that not everyone was as passionate about
Well-Architected as Erin and I, so my draft ended up being a template
for other areas, and I ended up writing "reliability" as well.
Everyone else was busy with their day jobs, and so Erin and I
ended up co-authoring the whole document, using the materials for each area.
Through this process we renamed them "pillars", and worked out that having
the questions as "open questions" was less accusatory, and more likely to
get an answer. We settled on "workload" to talk about the thing the customer
was building, and "Framework" for what the document was.

[^1]: Don't let Fitz name things.
[^2]: Yes I made these mistakes too.
[^3]: Where a large number of customers were impacted. They
stopped using this term when it was realised that if you have millions
of customers even a small % impacted is technically a LSE. Also customers
did not care how many other people were impacted, they cared that *they* were.
[^4]: Douglas Adams, The Restaurant at the End of the Universe
[^5]: It was Amazon tradition to send a problem-owner a single character emails to express this "?" unhappyness.
[^6]: Don't ask.
[^7]: This is the cause of a lot of problems, but also allowed us to progress.
[^8]: Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models
[^9]: This was quick to create, and then instantly a source of pain going forwards. Medium term it was replaced with an internal tool.