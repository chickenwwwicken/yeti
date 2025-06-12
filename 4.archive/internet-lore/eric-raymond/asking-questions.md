## How to Ask Questions the Smart Way
[link](http://catb.org/~esr/faqs/smart-questions.html)

### Introduction
In the world of hackers, the kind of answers you get to your technical questions depends as much on the way you ask the questions as on the difficulty of developing the answer. 
This guide will teach you how to ask questions in a way more likely to get good answer.

Now that the use of opensource has become widespread. 
You can often get as good answer from experienced users as from hackers. 
This is good thing: users tend to be more tolerant to failures of newbies.

The first thing to understand is that hackers actually like hard problems and good, 
thought-provoking questions about them.
If you give an interesting question to chew on they be grateful to you:
good questions are stimulus and gift.
Good questions help develop understanding, often reveal problems  not noticed.
"Good question!" is a strong and sincere compliment. 

What we are, unapologetically, is hostile to people who seem to be unwillling to think or to do their own homework before asking questions. 
People like that are time sinks --  they take without giving back, and they waste time we could have spent on another question more interesting and another person more worthy of an answer. 
We call people like this lusers. (L-users)

We realize that there are many people who just want to use the software we write, and who have no interest in learning technical details. 
For most people a computer is merely a tool, a means to an end; 
they have more important things to do and lives to live. 
We acknowledge that, and donn't expect everyone to take an interest in tech matters that fascinate us. 
Nevertheless, our style of answering questions is tuned for people who do take such interest and are willing to be active participants in problem-solving. 
That's not going to change. 
Nor should it; if it did, we would become less effective at the things we do best. 

We're largely volunteers. We take time out of busy lives to answer questions, and at times we're overwhelmed with the, . 
So we filter ruthlessly. In particular, we throw away questions from peoplle who appear to be losers in order to spend our question-answering time more efficiently. 

We're not asking you to genuflect to us -- in fact, most of us would love nothing more than to deal with you as an equal and welcome you into our culture, if you put in the effort required to make that possible. 
But it's simply not efficient for us to try to help people who are not willing to help themselves. 
It's OK to be ignorant. 
It's not OK to play stupid. 

So, while it isn't necessary to already be technically competent to get attention from us, 
it is necessary to demonstrate the kind of attitude that leads to competence -- 
alert, thoughtful, observant, willing to be an active partner in developing a solution. 
If you can't live with this sort of discrimination, we suggest you pay somebody for a commercial
support contract instead of asking hackers to personally donate help to you. 

The best way to get a rapid and responsive answer is to ask it like a person with smarts, confidence,
and clues who just happens to need help on one particular problem. 


## Before You Ask

Before asking a technical question, do the following:

1. Try to find an answer  by searching the archives of the forum.
2. Try to find an answer by searching the web
3. Try to find an answer by reading the manual
4. Try to find an answer by reading a FAQ
5. Try to find an answer by inspection or experimentation
6. Try to find an answer by asking a skilled friend
7. If you're a programmer, try to find an answer by reading the source code. 

When you ask your question, display the fact that you have done these things first; 
this will help establish that you're not being a lazy sponge and wasting people's time. 
Better yet, display what you have learned from doing these things. 
We like answering questions for people who have demonstrated they can learn. 

Use tactics like doing a  Google search on the text of whatever error message you get.
This might well take you straight to fix documentation or a mailing list answering question. 
Saying you googled it is a good thing to do requesting help, 
if only vecause it records what searches won't help.
It will also help to direct other people with similar problems to your thread by linking the search terms to what will hopefully be your problem and resolution thread. 

Take your time. 
Do not expect ot be able to solve a complicated problem with a few seconds of Goggling. 
Read and understand the FAQs sit back relax and give the problem some thought before asking.
They will be able to tell from you questions how much reading and thinking you did. 

Prepare your question, Think it through.
Hasty-sounding questions get hasty answers, or non at all. 
The more you do to demonstrate that having put thought and effort into solving your problem before seeking help, the more likely you are to actually get help. 

Beware of asking the wrong question. 
If you ask one that is based on faulty assumptions, Random hacker is quite likely to reply
with a uselessly literal answer while thinking "Stupid Question" , 
and hoping the experience of getting what you asked for rather than what you needed will 
teach you a lesson. 

You are not entitled to an answer. 

## When you ask

#### Choose your forum carefully

Hackers blow off questions that are inappropriately targeted in order to try to protect their communications channels from being drowned in irrelevance. 

#### Stack Overflow

Search, then ask on [Stack Exchange](https://stackexchange.com/sites) 
Unix-Linux [Stack Exchange](https://unix.stackexchange.com/)
Super User is for questions about general-purpose computing. 
Stack Overflow is for questions about programming. 
Server Fault is for questions about server and network administration. 

Several projects have their own specific sites.

#### Meaningful, Specific subject headers

**Stupid:**
HELP! Video doesn't work properly on my laptop!

**Smart:**
X.org 6.8.1 misshapen mouse cursor, Fooware MV1005 vid. chipset

**Smarter:**
X.org 6.8.1 mouse cursor on Fooware MV1005 vid. chipset - is misshapen

"object deviation" is used by many tech support organizations, 
"object" part specifies what thing or group of things is having a problem
"deviation" part describes the deviation from expected behaviour.

The process of writing an "object-deviation" description will help you organize your thinking about the problem more in detail. 
What is affected? Just the mouse cursor oor other graphics too?
Is this specific to the x version of x? is this specific to shipsets? 
Is this specific to model x? 
A hacker who sees the result can immediately understand what it is that you are having a problem with and the problem you are having at a glance. 

More generally, imagine looking at the index of an archive of questions, with just the subject lines showing. 
Make your subject line reflect your question well enough that the next person searching the archive with a question similar to yours will be able to follow the thread to an answer rather than posting the question again. 

If you ask a question in a reply, be sure to change the subject line to indicate that you're asking a question. 

#### Grovelling is not a substitute for doing your homework

Some people who get that they shouldn't behave rudely or arrogantly, demanding an answer, retreat to the opposite extreme of grovelling. 

#### Describe the problem's symptoms, not your guesses

It's not useful to tell hackers what you think is causing your problem. (If your diagnostic theories were such hot stuff, would you be consulting others for help?) So, make sure you're telling them the raw symptoms of what goes wrong, rather than your interpretations and theories. Let them do the interpretation and diagnosis. If you feel it's important to state your guess, clearly label it as such and describe why that answer isn't working for you.

Stupid:
I'm getting back-to-back SIG11 errors on kernel compiles, and suspect a hairline crack on one of the motherboard traces. What's the best way to check for those?

**Smart:**
My home-built K6/233 on an FIC-PA2007 motherboard (VIA Apollo VP2 chipset) with 256MB Corsair PC133 SDRAM starts getting frequent SIG11 errors about 20 minutes after power-on during the course of kernel compiles, but never in the first 20 minutes. Rebooting doesn't restart the clock, but powering down overnight does. Swapping out all RAM didn't help. The relevant part of a typical compile session log follows.

Since the preceding point seems to be a tough one for many people to grasp, here's a phrase to remind you: "All diagnosticians are from Missouri." That US state's official motto is "Show me" (earned in 1899, when Congressman Willard D. Vandiver said "I come from a country that raises corn and cotton and cockleburs and Democrats, and frothy eloquence neither convinces nor satisfies me. I'm from Missouri. You've got to show me.") In diagnosticians' case, it's not a matter of skepticism, but rather a literal, functional need to see whatever is as close as possible to the same raw evidence that you see, rather than your surmises and summaries. Show us.

#### Describe your problem's symptoms in chronological order


#### Describe the goal, not the step
Stupid:
How do I get the color-picker on the FooDraw program to take a hexadecimal RGB value?

**Smart**:
I'm trying to replace the color table on an image with values of my choosing. Right now the only way I can see to do this is by editing each table slot, but I can't get FooDraw's color picker to take a hexadecimal RGB value.

The second version of the question is smart. It allows an answer that suggests a tool better suited to the task.


#### Dealing with rudeness

Much of what looks like rudeness in havker circles is not intended to give offense. 
Rather, it's the product of the direct, cut-through-the-bullshit communications style that is natural to people who are more concerned about solving problems than making others feel warm and fuzzy. 

When you perceive rudeness, try to react calmly. 
If someone is really acting out, it is very likely a senior person on the group will call him or her on it. 
If that doesn't happen and you lose your temper, it is likely that the person you lose it at was behaving within the hacker community's norms and you will be considered at fault. 
This will hurt your chances of getting the information or help you want.

On the other hand, you will occasionally run across rudeness and posturing that is quite gratuitous.
The flip-side of the above is that it is acceptable form to slam real offenders quite hard, dissecting their misbehavior with a sharp verbal scalpel. 
Be very, very sure of your ground before you try this, however. 
The line between correcting an incivility and starting a pointless flamewar is thin enough that hackers themselves not infrequently blunder across it; 
if you are a newbie or an outsider, your chances of avoiding such a blunder are low. 
If you're after information rather than entertainment, it's better to keep your fingers off the keyboard than to risk this. 

(Some people assert that many hackers have a mild form of autism or Asperger's Syndrome, and are actually missing some of the brain circuitry that lubricates “normal” human social interaction. This may or may not be true. If you are not a hacker yourself, it may help you cope with our eccentricities if you think of us as being brain-damaged. Go right ahead. We won't care; we like being whatever it is we are, and generally have a healthy skepticism about clinical labels.)

jeff bigler's observations about [[tact-filters]] are also relevant and worth reading. 

## On Not Reacting Like a Loser

Odds are you'll screw up a few times on hacker community forums -- in ways detailed in this article, or similar. 
And you'll be told exactly how you screwed up, in public.

When this happens, the worst thing you can do is whine about the experience, claim to have been verbally assaulted, demand apologies, scream, hold your breath, threaten lawsuits, complain to people's employers, leave the toilet seat up etc. Instead:

Get over it, it's normal. In fact it's healthy and appropriate. 

Community standartds do not maintain themselves:  
They're maintained by people actively applying them, visibly in public. 
Don't whine that all criticism should have been conveyed via private e-mail: That's not how it works. Nor is it useful to insist you've been personally insulted when someone comments that one of your claims was wrong, or that his views differ. Those are loser attitudes.

There have been hacker forums where, out of some misguided sense of hyper-courtesy, participants are banned from posting any fault-finding with another's posts, and told “Don't say anything if you're unwilling to help the user.” The resulting departure of clueful participants to elsewhere causes them to descend into meaningless babble and become useless as technical forums.

Exaggeratedly “friendly” (in that fashion) or useful: Pick one.

Remember: When that hacker tells you that you've screwed up, and (no matter how gruffly) tells you not to do it again, he's acting out of concern for (1) you and (2) his community. It would be much easier for him to ignore you and filter you out of his life. If you can't manage to be grateful, at least have a little dignity, don't whine, and don't expect to be treated like a fragile doll just because you're a newcomer with a theatrically hypersensitive soul and delusions of entitlement.

Sometimes people will attack you personally, flame without an apparent reason, etc., even if you don't screw up (or have only screwed up in their imagination). In this case, complaining is the way to really screw up.

These flamers are either lamers who don't have a clue but believe themselves to be experts, or would-be psychologists testing whether you'll screw up. The other readers either ignore them, or find ways to deal with them on their own. The flamers' behavior creates problems for themselves, which don't have to concern you.

Don't let yourself be drawn into a flamewar, either. Most flames are best ignored — after you've checked whether they are really flames, not pointers to the ways in which you have screwed up, and not cleverly ciphered answers to your real question (this happens as well).
