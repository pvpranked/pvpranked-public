# PVP Ranked

I want to download this mod: https://modrinth.com/mod/pvpranked
I want to report a problem with this mod: https://github.com/pvpranked/pvpranked-public/issues
I want to join the Discord: https://discord.gg/2dTYcaxaFX
I want to make a suggestion! : either join the discord and find #suggestions or make an issue, your choice

Hi!

PVP Ranked is a project to allow all 1.9 PVPers to compete against each other with a functional ranking system and a unified, good-quality experience. It will be an ideal tool for both practicing and truly having a proper competitive scene in PVP.

PVP Ranked is a mod that users run, not a Minecraft server. Players can select what gamemodes they would like to queue for from a main screen accessed in the title screen. They will then be matched against an opponent in one of those modes, finding the player closest to you in skill, optimized for low ping.

Once in a match, players 1v1 to the death until they've won enough rounds to win the match. 
Once the match is over your Skill Rating, SR, is corrected based on the ELO rating system using the results of the match. In general, winning a match against someone of equal skill to you will increase your SR, and losing will decrease it. Players are rated on SRs 1-6000, a higher SR denoting a higher skilled player. The SR spread is split into 6 ranks: Copper, Silver, Gold, Diamond, Masters, and Champion. 


## Full Feature Summary:

* Matches you against players near your skill rating and of a similar region, to ensure low ping
* Patched the most significant cause of Ghost Totems
* New volume options: Change the volume of every PVP Sound effect individually! (crits, totem pops, etc.)
* Anticheat: Client-side anticheat checks your mods list against a whitelist

# Is PVP Ranked Safe?

Yes. Although this isn't a legal guarantee, nothing bad can happen to you just because you use PVP Ranked.
* Is the internet part safe? - Yes. Although you are joining someone else's single-player world as if by LAN, all the internet traffic goes through the PVP Ranked servers first. If you're worried about more technical internet security, PVP Ranked uses websocket connections through HTTPS and HTTPS itself, nothing else.
* Is the mod itself safe? - Yes. I (pvpranked is my discord username) am the only developer and there's nothing bad in it. I'm hoping when PVP Ranked gets larger, I can find a respected PVPer who also understands code so that I can give access to the source code so the community doesn't have to take my word for it like they do with every other mod they've ever installed.
* Can other players hurt me at all? I am joining their single-player world, after all. - No! Normally there's maybe one or two ways they could try to get you, but both of them are completely shut down. It is literally completely safe.
    * No. Normally, LAN worlds can force new players to download a resource pack - this is disabled. The server cannot do it, and the mod will automatically reject anything another player tries to send you.
    * Couldn't they just... send me a virus over the internet? - Nope. Minecraft doesn't work like that. Short explanation: When you join any Minecraft server, the server can't just send you files. Anytime any server sends you anything, they send you a package in two parts. The first part is the type: for example, 'playerTeleportPacket'. The second part is the data - for a teleport packet it might be '4234, 80, -522', the coordinates you're being sent to. Anything that doesn't match one of those types is rejected. And the only type that lets them send you anything hurtful is when they send you the resource pack which is, as I said above, covered.
* What if they doxx me? I'm joining their server, so don't they have my IP address? - No. All of your communications with the other player is first sent through the PVP Ranked servers, then to the other player. This means the other player sees the IP address of the PVP Ranked servers and isn't able to access your own.

# Super technical details on how stuff works:

The general idea of PVP Ranked is this: 
Minecraft servers are so expensive to run because they have to simulate the world around every player. If you make an FFA server, like stray.gg and many other servers, then you can save money because you only have to simulate one area, and the amount of area you have to simulate doesn't increase with the number of players. But what if we had each player simulate their own match?

### Advantages: 
* Anyone can run a singleplayer world, especially considering that the PVP Ranked version of a singleplayer world:
  * Don't have to worry about mobs
  * Don't have to worry about terrain destruction for most modes
  * Don't have to generate fresh terrain
* I don't have to ruthlessly gut my playerbase for the $500/month I would need for a large server. As an Overwatch player, I do NOT want a monetization system that ruins the product.
* Incredible anticheat is now possible. PVP Ranked has a large whitelist of mods that are allowed (will be

* **We can have many, many regions.** Adding a server costs us $10/month. We plan to have servers in NA West, East coach America, EU, eventually SA and Asia, and possibly Australia the Middle East
* We will also offer a service where you can just pay us to add a new region.

### Disadvantages:
* Players with weak PCs might have trouble - SOLUTION: if your PC is weak enough, it will make the other player the host
* Increased ping - Unless you don't have a PVP Ranked server in your region, the extra ping is negligible. There have been no ping problems so far in early testing.

### How it actually works

When you enter a match, one player is picked to host the match. An internal singleplayer world reserved for PVP Ranked testing is reset and then opened. First, the host joins, and then 

You begin talking to another player *through* whichever PVP Ranked server is closest. If you want to send a message to the other player, you first send it to the PVP Ranked server, and the server sends it to them.



