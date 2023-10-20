# Pokemon-Time-Series-Analysis
An analysis on the Smogon Singles Competitive pokemon data from 2015-2023

Project Aim:
To determine the direction of the metagame.
Are older generations of pokemon being outclassed by newer pokemon being introduced?
Is there a seasonality behind certain pokemon being used?
Is there a correlation between certain pokemon being used.
Is the usage of pokemon in tournaments different to the standard user usages or is there a wider variety used at higher levels of competition?

Context:
Pokémon is a popular video game series created by Satoshi Tajiri and GameFreak. It started in 1996 with games like Pokémon Red and Blue. The games are all about catching and training creatures called Pokémon.

The company Game Freak makes most of the games, and there are many different versions with new Pokémon and stories. There are also games called spin-offs where the mechanics are changed such as Pokemon Pinball or Pokemon Snap, however we are looking at the main games and how the world has taken it to a competitive level, where battling and team building takes priority.

There are different types of moves a Pokemon can use which can be categorized into Status Moves, Stat Boosting/Reducing Moves , Attacking Moves. There are also other mechanics such as type effectiveness, where certain moves will deal more damage to others, natures and IV/EV training which are hidden values that boost stats of pokemon to a certain degree, which can be manipulated with mathematics to make pokemon last longer in battle or hit harder.

With any nature of competition, finding an advantage by gaining any information possible is considered crucial. This is where the term “Metagame” comes in. Metagame is normally used to describe a game within a game, however in a roleplaying perspective it is the use of information outside of the mechanics to help drive decisions made within the game. An example in parallel would be in Dungeons and Dragons to use a weapon that uses two six sided dice rather than one twelve sided die as it will give a better average of damage and minimize the risk of getting lower damages. 

In the context of pokemon it would be knowing which pokemon have better attacks or can survive for longer as well as knowing what moves each pokemon can learn.
This means that in a competitive level, players would be looking at choosing pokemon that are statistically more advantageous or bring different strategies and avoid pokemon that are one dimensional. Also it is never just a one on one fight, its teams of pokemon fighting. Six pokemon fighting six rival pokemon. So strategies around switching, boosting and recovering come into play. 

Competitive Pokémon battles are unlike the familiar single-player games. Here, you face off against real people, and they're out to win and can make decisions based on information that is not available to an algorithm. Choosing Pokémon based on favorites won't cut it. To succeed, you'll need strategic picks.

In these battles, “switching” is a game-changer. Opponents won't let their Pokémon faint; they'll switch to gain an advantage. Predictable moves can be exploited to gain an advantageous situation.Luck plays a role, too. Critical hits, status effects, and imperfect accuracy can influence battles. Individual wins don't mean much; consistency matters more. Even top players can lose, but they maintain strong win-loss ratios in the long run.

There are officially run tournaments by Nintendo and by GameFreak where the nature of battling sees players fight 2v2 in a best of three format allowing the choice to bring four pokemon out of a team of six. Smogon, an online globally recognised authority on competitive pokemon, runs tournaments as well for prestigious battlers that runs in a similar format but also runs what is considered the most popular format which is Singles where it pits 1v1 with a selection of 6 pokemon on a team. 

There are extra rules kept in place to ensure good sportsmanship such as Sleep Clause and a Species Clause that means you can only bring one of each species (can’t run six of the same pokemon). These extra clauses are included to make sure the game is enjoyable as well remove over-powerful strategies, stalemates and less reliant on luck.

The next thing to understand is the tiering system implemented. Although there are no tiers in the actual game, pokemon can fall under natural categories where they are used because they are stronger or naturally peoples favorites for differing reasons. Tiers create distinct metagames, grouping Pokémon by strength and usage. Lower-tier formats give weaker Pokémon a chance to stand out. Tiers allow tailored rules for each metagame, ensuring more Pokémon are viable and balanced. Some Pokémon are banned from tiers if too powerful, for a diverse metagame.

AG - Anything Goes
Ubers - German for above competition
OU - Overused
UU - Underused
RU - Rarely Used
NU - Never Used
PU - An expression of disgust
ZU - Zero Used
Limbo - Pokemon that are not rated for competitive play

In order for a pokemon to be considered OU it has to be used on 1/20 teams. You can use pokemon of lower tiers in higher tiers, however you should expect them to be outclassed by pokemon that fall in that tier. Bringing a ZU pokemon to OU would most likely result in a loss due to that pokemon being a hindrance to the team or an empty slot that is better filled by something else.

In order for a pokemon to be banned, the community runs a suspect test to see if the metagame is better without the tested pokemon and players are required to meet a certain criteria to vote. This is a combined form of ELO rating and a Glicko rating which is to determine if a player is skillful enough and knowledgeable in the tier/metagame to have a say in determining the future of the tier.

Scope:
We will analyze each generation's own OU platform, which is considered by most to be the commonly played tier and is used for most competitive battling and tournaments. It is a tier that bans as few Pokemon as possible and places placement on usage rather than “power” which is difficult to gauge objectively. A pokemon is OU if it shows up in 1 out of 20 teams.You can use pokemon of lower tiers in OU however which creates the diverse field.

The data available starts November 2014, however we will start from 2015 as using only two months to compare to an entire year of development is not accurate. 

Some generations have been available prior to the data collection. This means some generations have been played for a longer time and the metagame will be stabler and more defined. The time frames of each of the generations are below:

Generation 1: 1996 - 1998
Generation 2: 1999 - 2001
Generation 3: 2002 - 2005
Generation 4: 2006 - 2009
Generation 5: 2010 - 2012
Generation 6:  2013 - 2016
Generation 7:  2016 - 2018
Generation 8:  2019 - 2021
Generation 9:  2022 - Present

Because previous generations can be played in later years on the platform, we will use that data as well to see if the influences of successor generations affect usage statistics of previous generations as novelty ideas get introduced as time goes on. 

NB: Generation 6 is incomplete as its data encompasses 2015 rather than the true start which is 2013. This is due to Showdown not existing back then and its predecessor not containing the records.

How is the data Gathered?
The data is pulled from the index of stats on Smogon ( https://www.smogon.com/stats/ ) which has pooled the usage statistics of pokemon by players on Pokemon Showdown. A complete collection of all files used will be available.

The data is stored in text files. It is also split depending on the level of usage at different levels of play, normally split between 0-1500 ELO, 1501 - 1630 , 1631-1759 and 1760 and over. 

This creates a split of four skill levels. If there is a suspect testing the usage of one pokemon being destructive to the metagame it is stored under a separate test flag named OU suspect test.
To address the issue of usage statistics being split at skill levels, we will maintain this division as 4 skill levels in line with the Dreyfus model, labeled Novice, Competent, Proficient and Expert.
