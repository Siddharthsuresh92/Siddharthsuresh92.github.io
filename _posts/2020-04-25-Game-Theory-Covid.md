---
title:  "Game Theory & COVID19"
last_modified_at: 2020-06-05T16:00:00-04:00
image:
    path: /assets/images/Covid-stat.png
    thumbnail: /assets/images/COVID.png
---
The Coronavirus Disease or better know as COVID-19, caused by the severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2) has had a profound impact all over the world (affecting some countries way more than others).

The World Health Organization (WHO) decalred COVID-19 a Public Health Emergency on 30th January 2020 and later decalred it as a pandemic on 11th March 2020.

One big debate has been about the infection rate and the mortality rate of this disease, some comparing it to the likes of flu. Comparing COVID-19 to a flu virus is literally the height of stupidity. On one hand we the flu for which we do have prediction models for the virus strain each year and subsequently a flu shot each year. On the other hand we have COVID-19 which is never existed before this and **NO HUMAN** on earth has natural immunity against it and ofcourse we have no shots for it either.

Check out this really cool visualization that provides up to date information on COVID-19: [COVID-19](https://informationisbeautiful.net/visualizations/covid-19-coronavirus-infographic-datapack/)

Bear in mind that the infection rate and mortality rate depends on a lot of different factors such as:
1. Rate of testing
2. Reactive testing vs. Proactive testing policy
3. Social distancing policies

While most countries locked down with strict measures, US was somewhat lenient on those social distancing policies. I wanted to use Game Theory to see what the dominant strategy really is with respect to going out and staying home.

My first attempt at it involved two players: The people represent Player 1 and the virus represents Player 2.

Player 1 has the following moves:
1. Stay at home and practice social distance
2. Live life like in the pre-COVID era

Player 2 has the following moves:
1. Be deadly and result in deaths
2. Be mild and not life threatening

Now, the strategy has to be from the point of view of Player 1 because Player 2 doesn't really have a choice, there is a ground truth to it's move which we will find out sooner than later.

| COVID\People | Stay home | Go out |
|:------------------:|:--------------:|:---------:|
| Deadly             |      _, +1         |    _, -1      |
| Mild                 |         _, 0        |     _, 0     |

These payoffs were calculated based on the impact on someone's health. If the virus turns out to be deadly, staying home is better than going out and so the payoffs end up being +1 and -1 respectively. But in case the virus is mild, the payoffs are 0 for whichever strategy people choose because it's the same thing. So in case the virus is mild, people should be indifferent about their choice.

This makes the strategy to **Stay home** dominant irrespective of whether or not COVID-19 is deadly or mild. Although this is called a weakly dominant strategy since people are indifferent when the virus is mild. 

I had a really hard time understanding why anyone would think it's a hoax and keep living without any concern of a pandemic. I understood that there is a possibility that the virus isn't too bad but the lack of vaccines makes it difficult to take it lightly. But I never understood why people would rather risk their lives than listen to doctors and scientists.

That's when I realized something. Not everyone in this world is as priviledged as I am. For me it was fairly easy to transition to a life with no social contact and no stepping outside the house. But for a lot of people, their entire survival depended on their work which cannot be done remotely or by sitting at home. People were losing their jobs, their livelihood and the ability to pay rent or even get food.

The payoffs I calculated were wrong because the point of view was narrow and only related to the health of people in the world. But health also extends to finanial health and not just physical health. It was important to include that while designing these payoffs.

The second iteration looks something like this:

| COVID\People | Stay home | Go out |
|:------------------:|:--------------:|:---------:|
| Deadly             |      _, +1         |    _, -1      |
| Mild                 |         _, -1       |     _, 0     |

The difference here is that staying home by risking their livelihood is detrimental for a lot of people in case the virus is mild. But given these payoffs there is no dominant strategy anymore. Since we do not have payoffs for COVID-19, there isn't any way to ascertain if a weak dominance equilibrium exists. Payoffs don't really exist for COVID-19 because it doesn't fulfil the assumptions of game theory and moreover it's not "really" a player that is rational, doesn't have any economic utility and honestly doesn't have a choice in being deadly/mild.

At this point it's obvious that this whole problem cannot be designed as a game, but it was still fun to think about trying to convince people to practice social distancing through logic.

It's really anybody's guess at this point what one should do in case they have the freedom to choose between staying home or going out to work. While some argue that for the sake of protecting the vulnerable and preventing deaths, cities should be locked down, others argue that the economic impact will be catastrophic if businesses remain closed. I think the right thing to do here would be to find a middle ground. Protecting the vulnerable by enforcing strict social distancing norms and gradually opening up businesses, with the backdrop of proactive testing could do the trick.
