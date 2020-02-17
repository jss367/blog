---
layout: post
title: Pencils, Paper, and People - A (non)-Revolutionary Idea for Elections
categories: [Politics]
---

Why do we need specialized software for elections?

The process of voting isn't that hard. It just isn't. That's why it's especially painful to see the United States completely trip over itself 



This is quite a flexible framework as well. It would allow for many things - first past the post, rank choice voting (my preference), etc. You could do it all in one day or spread the primaries out over months like it is today. It allows for rank choice voting. You could even use it in a general election. Let's look at how it would work in a place like California.

Everyone in California goes to the polls. Yes, physically except in the case of extenuating circumstances (People immobilized in hospitals, etc.). You could even do a vote by mail approach. You could make exceptions for these cases but I'm not going to go into detail on that because I don't want to miss the main point. 

So everyone goes into their polling stations and gets a ballot. They see all the candidates who are running for president and rank them according to their preferences. There can be many candidates from the same party or no party at all. You no longer need a primary process to reduce the number of candidates to one from each party. (Although there still may be practical reasons a party conducts a primary system to reduce the number of candidates.) So you rank all the candidates from 1 to, say 9, and put your ballot in the ballot box.

Once the polls are closed the ballots are counted up. A group of people lead by an independent and containing an observer from each party, counts up all the votes from a given box (and, for extra security, this could be recorded and even live-streamed). They record the number of first-choice votes each candidate has. From there they call into a district level, 


There were about 116,990 polling places in the US for the 2016 election ([source](https://www.eac.gov/documents/2017/11/15/eavs-deep-dive-poll-workers-and-polling-places)). This is to count of the nearly 139 million votes that were cast in the presidential race ([source](https://www.businessinsider.com/trump-voter-turnout-records-history-obama-clinton-2016-11)). So that's about 1200 votes per polling place. Say you split that into four groups to count up the votes. At 5 seconds a count that 25 minutes to count up all the votes.

Then you need to aggregate them up to higher levels. California has about 12% of the US population so we'll look at that. So that's about 14,000 polling places in California. Each polling place calls up to a district level, which, we'll say, talks to 25 polling places. This means they'll need 560 such districts. They could do a video chat where the independent and the observing party members are all present. Once the polling place has tallied up all their votes, they send a message to the district office that they are ready, and whenever the district office calls the polling place. 

This is really resistant to attacks (yes, I know about deep fakes). First, the call is from one pre-set account to another - it's a Skype or Google Hangouts call from a known entites (e.g. the Smalltown Middle School Voting Place's Skype account) to a known entity (the district vote tallying place). It would be basically to create a deep fake video, hack into the account, transmit the fake video, then somehow get the real people to not dial in, which the district tallying center would obviously see that there had been a problem. All of these conversations are, by the way, recorded and could even be live-streamed (although doesn't have to be; that's a separate topic).

OK, back to logistics. So we have a district tallying center talking to 25 different polling places. They only need to relay the number of first-place votes for each candidate and they know they need to be efficient, so let's say it takes 30 seconds per polling place, with another 10 seconds dialing and connecting time, so 40 seconds total. We'll throw a little buffer on the result and say it takes 20 minutes to get through the whole process.

So now California has 280 districts with this information. They compile the results themselves. Again, they can use general software for this. A simple calculator or spreadsheet is all they need. After they take 5 minutes to compile their results, they let the regional office know they are ready. Then, following the same basic process as before, the regional office video chats with all the district offices. This takes another 20 minutes and leaves the results at 23 regional level vote tallying places across the country. 5 minutes to tally the votes and another 20 minutes to finish the process at the state level and you have your results - the number of first-place ballots cast for every candidate at the state. At this point I think it would make sense to publically announce the results (which could also be done at every level by live-streaming it) and every network channel and election calculating hobbiest would compute the national numbers. It also wouldn't take much time because by the time California was done every other state would be finished.

So, in total, we have

Polling places close: t0

(Vpp / G) * T_v + Tp_d * P_d + T_d + Td_r * D_r + T_r + Td_r * D_r

Vpp - votes per polling place
G - number of groups counting votes
T_v - time to count individual votes
Tp_d - average time it takes polling place to tell the district
P_d - number of polling places per districts
T_d - time it takes district to sum up results
Tp_d - average time it takes district to tell the regional level
D_r - number of districts per region
T_r - time it takes regional people to sum up results








They already have pictures of the people they'll be working with. There's also someone running the polling station who the district level knows personally, who can make judgements in the case of unexpected emergencies.



(If there are a lot of candidates you might want to reduce the number of candidates )



Again, this is just a specific suggested implementation of a larger idea. If you don't like this specific implementation, you could tinker with it (and email me with your thoughts). For example, you could still do the electoral college if you're a fan of antiquated ideas.


The most important aspect of this is that there is no way to disrupt the process in a way that scales. Let's say, you could go to a polling place and steal a box of votes and replace it with one stuffed with your own ballots. That's not good but on a federal level, it just doesn't scale. You can't possibly mess up enough ballots to cause that big of an impact. An impact is not good, but I'm just trying to look at the larger picture. Consider the case where everyone is using software, and there's a bug or an attack that messes it up. Suddenly, everything that uses this software could be compromised.


What do you need for this approach? Pencils, paper, and people. 


Why is this so hard? I think there are three reasons:
1. Entrenched interests - I think this is the default one people will think of and it's the least significant. Sure, every who was voted into power today was voted in using the current system (at the time they were elected), and that's going to have some effects. But I don't think, in *this* case, this is a big effect.
2. Status quo bias - as I've written about before, I think this is the MOST underappreciated bias that affects us today. The bias of this is what we've done so this is what we'll always do is strong.
3. 

How important is it to get this right? I think spending extra money and waiting all night to get the right answer are worth it.

You can allow early voting, etc.


Now you could do a computer for this last part, but you don't have to. Spend the time. As I've already said, I think [we should consider having MORE money in our elections]. You could do computer vision on the ballots, use some of the techniques developed by Google Books to flip through them quickly. At the minimum, you could automate the 

The ballots should have the names randomized on them. You could use a computer in this process as the ballots would be created far in advance of the election and there are plenty of simple ways to verify that this is working as expected.


I think xkcd (as usual) summarizes the [software engineer's belief about this rather well](https://xkcd.com/2030/).

The concern about mail-in voting is that you lose the secreacy of the process, as you can't be sure that someone didn't watch someone else vote or force them to vote a certain way. Even then, I think the loss in this for extenuating circumstances (like U.S. citizens overseas) is less than anything using technology.


Pre-election software is fine. General software is fine. They are not specified which one to use. Whatever their preference is. Something commonly used and not specially built.

Want to optimize the number of districts and regions? You can do it mathematically!

Who cares if it's repetitive. It's safe, secure, transparent as we want it to be, and unhackable. For transparency, you could either record and release or live stream every step of the process.

