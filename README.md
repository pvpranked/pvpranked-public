# PVP Ranked

* I want to download this mod: https://modrinth.com/mod/pvpranked  
* I want to report a problem with this mod: https://github.com/pvpranked/pvpranked-public/issues  
* I want to join the Discord: https://discord.gg/2dTYcaxaFX  
* I want to make a suggestion! : either join the discord and find #suggestions, or [make an issue](https://github.com/pvpranked/pvpranked-public/issues), your choice

Hi!

PVP Ranked is a project to allow all 1.9 PVPers to compete against each other with a functional ranking system and a unified, good-quality experience. It will be an ideal tool for both practicing and truly having a proper competitive scene in PVP.

PVP Ranked is a mod that users run, not a Minecraft server. Players can select what gamemodes they want to queue for from a main screen accessed in the title screen. They will then be matched against an opponent in one of those modes, finding the player closest to you in skill, optimized for low ping.

Once in a match, players 1v1 to the death until they've won enough rounds to win the match. 
Once the match is over your Skill Rating, SR, is corrected based on the ELO rating system using the results of the match. In general, winning a match against someone of equal skill to you will increase your SR, and losing will decrease it. Players are rated on SRs 1-6000, a higher SR denoting a higher skilled player. The SR spread is split into 6 ranks: Copper, Silver, Gold, Diamond, Masters, and Champion. 


# Full Feature Summary:

* Matches you against players near your skill rating and of a similar region, to ensure low ping
* Patched the most significant cause of Ghost Totems
* New volume options: Change the volume of every PVP Sound effect individually! (crits, totem pops, etc.)
* Anticheat: Client-side anticheat checks your mods list against a whitelist making hacked clients almost impossible
* Profile Screen, leaderboards, and everything else you could want
* Mod updates itself

# Planned for before release: (Next 1-3 months, more info in the discord)

* Statistics tracking for every mode that tracks all relevant and useful stats for the mod: For example, critical hit accuracy, shield block accuracy, critical hits per match, shield blocks per match, % of hits are critical hits, etc. Also available to you will be the average of that stat for players above, below, and at your skill so you can better understand your strengths and weaknesses.
* In the future it will also include techniques, such as p-crits, s-taps, auto-hitting, walkthroughs, etc. 

# Plans for the future:

#### Replay System
Replay viewer capable of replaying the match exactly as you experienced it in-game

#### The **Improvement Engine.**
An engine that tells you what you're doing wrong in your matches and what you should have done - built by Tier 3+ PVPers who want to help others learn.
The basis of the statistics engine is code that forms a timeline of every action throughout a match and stores it next to a replay file.  
But it will also be able to recognize patterns. Much of PVP is stringing together techniques - knowing when to p-crit, how to use spacing, how to follow up on a shield disable, what techniques are okay when your own shield is disabled - all things a computer can recognize
The pictured end result is one where you can open a replay file and see a timeline of every technique you used over the match, each marked with a rating on how good of a decision it was and what the best options were.
You might see that it marked a KB-hit trade as wrong, and when you hover over it, it informs you that you should be following up on a shield disable by getting close and critting or by comboing them.

#### Cosmetics and Monetization
Monetization will always be limited to cosmetics.
Here's the plan:
* Titles: Pick a title for below your name, some examples are: "Monarch", "I'm going bald", "my ping is higher", "Methpot" and basically anything else we think of (suggestions for this will open when it becomes a feature;) )
For $1.49, you can pick any title you want and own it. For some other amount, you can permanently get every title.
   * Note that some titles that are locked behind achievements, like "Diamond Contender" and "Peak #55 Worldwide"
* Colored lightning! Normally lightning strikes when you kill the opponent, but with this you can choose what color you want it to be.
* The ability to name your weapons in matches: This is cool, but it also lets you use Optifine texture packs.

Also, for somewhere around $10-15, you can get a massive package that basically includes every cosmetic.

#### Achievements
This seems like a cool thing I'll probably add eventually, the improvement engine framework will make this much easier since the match timeline thing it makes would be able to easily recognize something like winning a sword match without taking damage.

## Is PVP Ranked Safe?

Yes. We've taken steps to cover all the ways someone could attempt to harm you through PVP Ranked.
* Is the internet part safe? - Yes. Although you are joining someone else's single-player world as if by LAN, all the internet traffic goes through the PVP Ranked servers first. If you're worried about more technical internet security, PVP Ranked uses websocket connections through HTTPS and HTTPS itself, nothing else.
* What if they doxx me? I'm joining their server, so don't they have my IP address? - You cannot doxx others, or be doxxed, from joining a PVP Ranked match. All of your communications with the other player is first sent through the PVP Ranked servers, then to the other player. This means the other player sees the IP address of the PVP Ranked servers and isn't able to access your own.
* Is the mod itself safe? - Yes. I (pvpranked is my discord username) am the only developer and have put nothing malicious in. I'm hoping when PVP Ranked gets larger, I can find a respected PVPer who also understands code so that I can give them access to the source code so the community doesn't have to take my word for it like they already do with every other mod they've ever installed.
* What if they send me a recommended resource pack? - They can't! And if they do, you won't receive it. Normally, LAN worlds can force new players to download a resource pack - this is disabled. Players cannot send resource packs to each other, and even if they did the other player automatically rejects them, so you are safe.
* Couldn't they just... send me a virus over the internet if they can send me stuff? - Nope. Minecraft doesn't work like that. Short explanation: When you join any Minecraft server, the server can't just send you files. Anytime any server sends you anything, they send you a package in two parts. The first part is the type: for example, 'playerTeleportPacket'. The second part is the data - for a teleport packet it might be '4234, 80, -522', the coordinates you're being sent to. Anything that doesn't match one of those types is rejected. And the only type I'm aware of that lets them send you anything hurtful is when they send you the resource pack which is, as I said directly above, covered.

# Super technical details on how stuff works:

The general idea of PVP Ranked is this:  
Minecraft servers are so expensive to run because they have to simulate the world around every player. FFA Servers, like stray.gg and many other servers, are worse for gameplay but do cost less because they only have to simulate one area, and that amount of area doesn't increase with the number of players!  
But what if we had each player simulate their own match?

### Advantages: 
* Anyone can run a singleplayer world, especially considering that the PVP Ranked version of a singleplayer world:
  * Don't have to worry about mobs
  * Don't have to worry about terrain destruction for most modes
  * Don't have to generate fresh terrain
* I don't have to ruthlessly gut my playerbase for the $500/month I would need for a large server. As an Overwatch player, I do NOT want a monetization system that ruins the product.
* Incredible anticheat is now possible. PVP Ranked has a large whitelist of mods that are allowed (still being made), and no other mods are allowed. So using hacked clients is really really hard.
* We can add better sounds and better visuals to every part of the PVP experience. This means showing you your rank at the top of your screen, having a better hud to show you the score, and cool victory animations.

* **We can have many, many regions.** Adding a server costs us $10/month. We plan to have servers in NA West, East coach America, EU, eventually SA and Asia, and possibly Australia or the Middle East.
* We will also offer a service where you can just pay us to add a new region.

### Disadvantages:
* Players with weak PCs might have trouble - SOLUTION: if your PC is weak enough, it will make the other player the host
* Increased ping - SOLUTION: Unless you don't have a PVP Ranked server in your region, the extra ping is negligible. There have been no ping problems so far in early testing.

### How it actually works

When you enter a match, one player is picked to host the match. An internal singleplayer world reserved for PVP Ranked testing is reset and then opened. First, the host joins, and then PVP Ranked makes the world available for another player to join - the code is simlar to the code for Minecraft's "Open to LAN" functionality.

You begin talking to another player *through* whichever PVP Ranked server is closest. If you want to send a message to the other player, you first send it to the PVP Ranked server, and the server sends it to them.



# Liscense:
https://github.com/pvpranked/pvpranked-public/blob/main/LISCENSE.txt
