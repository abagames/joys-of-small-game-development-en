## Teaching Game Mechanics to AI

In the previous section, we listed the game mechanics of action mini-games as tags.[^1] We demonstrated that by randomly combining multiple tags, one could conceptualize games utilizing these mechanics. By using ChatGPT for this task, we may be able to come up with new game ideas.

We provided the following prompt to ChatGPT, asking it to act as a game designer:

> I want you to act as a game designer. Remember the following tags related to game mechanics. The tags are written in a format of 'Category: Name, "Description"', with one line for each tag. Randomly combine those tags and come up with a new game that contains only the game mechanics corresponding to that tag. Make that game an action mini-game that utilizes only a single button. The maximum number of tags that may be combined is 5. Describe what kind of game it is and the selected tags. Try to devise 5 different games without using the same game mechanic tags as much as possible.
>
> player: rotate, "The player character rotates."<br>
> player: reciprocate, "The player character reciprocates horizontally or vertically."<br>
> player: reflect, "The player character reflects upon colliding with a wall or object."<br>
> ...

The following tag list and their explanations continue in the tag list file,[^2] and the entire prompt contains all these tags.[^3]

The responses obtained are as follows:

> Game 1: Scaffold Jump<br>
> Selected tags: player: scaffold, on pressed: jump
>
> Description: In this game, the player controls a character that moves along scaffolds. The character constantly moves forward, and the player can make the character jump by pressing the button. The objective is to avoid falling off the scaffolds or hitting obstacles while collecting coins or power-ups. The game gets progressively faster and more difficult as the player advances.
>
> Game 2: Pinball Panic<br>
> Selected tags: player: circle, weapon: bounce, field: pins, on pressed: shoot
>
> Description: In this game, the player controls a circular character that bounces around a pinball-like field. The player can shoot projectiles by pressing the button, which bounce off the pins and destroy enemies. The objective is to survive as long as possible while racking up points by destroying enemies and collecting power-ups.
>
> Game 3: Springy Strings<br>
> Selected tags: player: string, player: bounce, field: gravity, on pressed: jump
>
> Description: In this game, the player controls a spring-like character that bounces around a zero-gravity field. The character can jump by pressing the button, which sends it bouncing higher into the air. The objective is to avoid obstacles and enemies while collecting power-ups and reaching the end of the level.
>
> Game 4: Wipeout Warriors<br>
> Selected tags: player: bar, field: water, obstacle: chase, weapon: wipe, on pressed: jump
>
> Description: In this game, the player controls a bar-shaped character that races through a water course filled with obstacles and enemies. The character automatically moves forward, and the player can make the character jump by pressing the button. The character can also use a wiping weapon to clear the way of obstacles and enemies. The objective is to reach the end of the course in the shortest time possible.
>
> Game 5: Color Conundrum<br>
> Selected tags: rule: match, rule: time limit, field: roughness, on pressed: turn
>
> Description: In this game, the player controls a character that must navigate a rough terrain while matching colors. The character automatically moves forward, and the player can turn left or right by pressing the button. The objective is to match as many colors as possible before the time runs out, while avoiding obstacles and enemies on the way.

With the game names, selected tags, and game descriptions provided, one can pick interesting games and potentially utilize them as game ideas.

For instance, consider Game 2 "Pinball Panic". In a pinball-like field filled with pins and enemies, the player shoots projectiles by pressing a button, which then bounce off pins to destroy enemies. Skillfully controlling the bouncing ball to hit enemies can be intriguing, perhaps with a pinball flipper to launch the ball.

How about Game 3 "Springy Strings"? In a gravity-free space, a spring-like character navigates by bouncing off obstacles and enemies, propelled by kicks or arm swings, perhaps.

Game 5 "Color Conundrum" envisions a top-down game where a player character navigates bumpy terrain, steering left or right with a button press to match colors while collecting like-colored items, and avoiding obstacles and enemies.

It would be quite convenient if ChatGPT could also implement the game, but that is understandably not feasible at the moment. Although when prompted with 'Implement Game 1 in p5.js.', it does output some code, it doesn't accurately reflect the game mechanics.

Teaching game mechanics tags to ChatGPT and having it combine them can be a good method for brainstorming the basis for game ideas. ChatGPT seems well-suited for such brainstorming applications.

---

[^1]: [Dissecting and Assembling Game Mechanics](../ideas/break_down_game.html)
[^2]: [action-mini-game-mechanic-tags/src/tags.csv](https://github.com/abagames/action-mini-game-mechanic-tags/blob/main/src/tags.csv)
[^3]: [combine_tags_with_chatgpt.md](https://github.com/abagames/action-mini-game-mechanic-tags/blob/main/combine_tags_with_chatgpt.md#prompt)
