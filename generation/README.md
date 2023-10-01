## Can Small Games Be Self-Generated?

I wish for a machine that can automatically generate small games. Developers would play the games generated by this machine; they would adopt the enjoyable ones and discard the uninteresting ones, thereby creating games solely through this process. It would be a dream machine.

The premise is that humans will review and select the games later; hence, it's acceptable if the majority of the outcomes are not interesting. What's more crucial is ensuring that the games possess a sufficient variety of mechanics upon generation.

Efforts to enable AI to create games have been ongoing for several years. The ANGELINA project [^1] proposes a method of generating new games by randomly combining mechanisms, like doubling, halving, or switching the signs (+/-) of variables such as the player's position or gravity, whenever a button is pressed.[^2] These buttons, upon being pressed, switch the state of variables, a mechanism referred to as Toggleable Game Mechanics (TGM), and are applied and evaluated in puzzle jump-action games from start to finish, with the aim of exploring various TGM applications.

A genetic algorithm is employed to select the appropriate group of TGMs from random combinations. The fitness for selection is gauged based on the extent of level movement before reaching the goal, with the player being moved in a specified manner. A game is deemed high-quality if moving around the level is essential to eventually reach the goal, and games in which the goal is unreachable are eliminated.

However, the games created through this method remain within a certain range of variation, and whether they constitute new games is a gray area. Conceiving new games is challenging even for humans, thus posing a substantial challenge for computers.

Recently, technologies that have the potential to break these constraints have emerged. Exemplified by ChatGPT, these technologies are embodied in AI chatbots equipped with Large Language Models (LLM).

---

[^1]: [Games By Angelina](http://www.gamesbyangelina.org/)
[^2]: [Mechanic Miner: Reflection-Driven Game Mechanic Discovery and Level Design (pdf)](https://www.possibilityspace.org/papers/evo13.pdf)