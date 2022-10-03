# HACKING LIGHT
#### Video Demo:  https://youtu.be/brd7t_-E8MM
#### Description:
Hacking Light - is a 2D turn-based game built with Unity Engine and C#, 
where you can fight in space with spaceships. There is no story (yet with this version), just turn-based fights inspired by Heroes of Might and Magic and Disciples II. Rules are simple: you pick your ships, begin a fight, take your turn and choose which enemy ship you want to attack. If you destroy all enemy ships, you win. Every successful round gives the player a 10 score. The whole game idea is to get as many as possible.

Players can build their own "stack" of units. Each ship has its abilities such as "paralyzing" the enemy vessel for 1 turn, improving team accuracy, or shooting at multiple targets. For this part, I coded allships.cs, where I described baseship as a basic class and make a couple of inheritances.

The main class game.cs describes all window(UI) logic, purchasing ships, managing rounds, calculating damage, and also keeping in memory credits/scores. Moreover, game.cs contains artificial intelligence for the enemy side, such as creating stacks and choosing priorities for the attack. For building stack, I made a simple auto-leveling (like is TES V: Skyrim or Fallout 3): the enemy always uses almost the same amount of credits, as the player. Sometimes, the Enemy AI even picks the same stack as the player! 

In battle, I used a simple AI "decision tree".  In most cases, the enemy will always choose to destroy the most damaged or dangerous ("disabler" or "intel") vessel. Also, I left a low percent of the possibility to attack a  player's random ship: just to make it not so boring.

The team which spends the lesser amount of credits 
always takes the first turn. So if you spend less, there is a bigger chance you will have an opportunity to proceed with the first attack.
The best way to achieve victory is by combining different types of vessels and their abilities. 

Script UI_Ship.cs is the second most complex script in this app. It describes the whole logic of visuals and behavior in-game: managing ship attacks, receiving damage, instantiating blasters or explosives effect. 

In this project I used coroutines - it's an amazing thing, which allows you to avoid blocking the whole stream and implement some methods "in parallel" to the main process. As you can see, in-game AI will take a half or the whole second to "think" - thanks to "coroutines", AI looks like it's a real player, not a machine. Also "coroutines" allow the game to wait for player input commands (clicking on buttons).

Scripts named with "Effect" part describe a logic for the visual part of the game such as particles, blaster shots, sound, attached to them, etc.

MainMenu.cs managing settings in the first scene, changes sound volume, fullscreen/windowed mode, and also displaying highscore on the main screen.

"UI_BuyShip" describes buttons in the purchase menu. The last one is not static - if you will add new ships in "AllShips.cs" and initialize in "Start" void method (AvailableShips.AddRange...), you will see the purchase menu will change itself too! So everything is dynamically (may I use this word?) linked.

Finally, "DoNotDestroy.cs" describes a logic for the Unity engine to make it real for listening to the same audio source through all scenes in-game.

The whole project took me 3 weeks. Also, it took me more than half-year to learn Unity basics. I also working on another project: political strategy on Unity engine, but it takes much more time to submit is as my CS50 Final Project.

Many thanks to CS50! 