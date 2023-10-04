## The Possibilities of One-Button Games

In game jams, a setting that limits interaction to just one button, creating what is known as a one-button game.

Unlike having a stick for movement in addition to one button, the term 'one-button game' here refers to games where only one button is utilized for all gameplay interactions.

The advantage of one-button games lies in their straightforward controls, making them easily operable on touch devices. Essentially, pressing a button executes the entirety of the player's available actions, eliminating almost the need for instructions. Moreover, on touch devices, simply tapping or holding anywhere on the screen facilitates control, circumventing the common issue of unresponsive virtual pads encountered in other games.

The downside, naturally, is the challenge of introducing action variations. Even simple lateral movements, easily achieved with a stick, necessitate somewhat unconventional controls, such as reversing direction each time the button is pressed.

Thus, when developing a one-button game, the critical question becomes how to introduce variation in game interaction with merely one button. In that regard, I'd like to categorize some of the one-button games I've created thus far based on their unique mechanics.

### Incorporating Unique Actions

Typically, in one-button games, the player executes the following actions upon button press:

- Reverse movement direction, or rotate 90 degrees.
- Jump or flap.
- Fire a shot.

For instance, in the game THUNDER that I created (playable by clicking the image), even with only two-directional movement, the game can be fashioned into a one-button game by creatively utilizing obstacles and bonus items. However, it lacks characteristics unique to one-button games.

[![THUNDER](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/thunder/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?thunder)

If the action initiated by button press is rarely seen in conventional games, it can strongly impress upon players the uniqueness of the one-button control scheme.

#### Teleportation

[![CYWALL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/cywall/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?cywall)

Pre-set points on the screen allow players to teleport to the nearest point upon a button press. This mechanic enables swift movement with just one button.

#### Splitting

[![DIVARR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/divarr/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?divarr)

Each button press causes a missile to split. While continuously pressing the button boosts attack power, implementing constraints, such as introducing targets that should not be hit, is necessary to prevent mindless button mashing.

#### Choice

[![JUMP ON](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/jumpon/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?jumpon)

At certain points, players choose actions like turning or hopping to another platform. It's essential that players clearly understand the choice-making moments and their implications, requiring thoughtful game field design and presentation.

#### Attribute Inversion

[![NS CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/nsclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?nsclimb)

Attributes, like magnetic poles, switch with each button press. The crux of the game design lies in determining which attributes to use and how they interact with the environment.

#### Other Special Mechanisms

[![LADDER DROP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/ladderdrop/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?ladderdrop)

Timely dropping of moving platforms and ladders, akin to a one-button falling-block game.

[![NUMBER LINE](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/numberline/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?numberline)

Summing flowing numbers, a rather peculiar example illustrating that actions assigned to the button can be very diverse.

### Utilizing Hold-Down Button Actions

While one-button games usually trigger actions upon button press, actions can also occur continuously while the button is held down.

#### Adjusting Angles or Distances

[![NUMBER BALL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/numberball/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?numberball)

Common in golf games, the angle increases gradually as the button is held down, and players must release the button at the right moment to hit the ball. In this game, floors disappear when the number on the ball matches the number on the floor, which is a quirky rule that differentiates it from traditional golf.

[![FROOOOG](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/froooog/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?froooog)

The frog's leap distance is determined by the duration the button is held down; a solution to the challenge of moving the player from one place to multiple locations with one button.

#### Stretching

[![PIN CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/pinclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?pinclimb)

A stick stretches while the button is held down and retracts upon release. The extended stick can hook onto objects, facilitating progress when combined with certain terrain features.

[![SQUARE BAR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/squarebar/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?squarebar)

When combined with geometric shapes, even just stretching can produce complex movements.

[![TAPE J](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/tapej/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?tapej)

The longer the stretch, the more points earned, but at a higher risk, creating a balanced risk-reward scenario.

#### Defending / Dodging

[![EMBATTLED](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/embattled/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?embattled)

While the button is held, players become invulnerable to bullets. But they would get run over by tanks if they remain stationary, so they need to lure tanks close, release the button to dodge vertically, and watch the tanks battle each other.

[![REFLECTOR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/reflector/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?reflector)

A defensive wall always shields below, reflecting enemy fire, but holding the button enables powerful counterattacks at the expense of a shrinking defense wall.

[![BAMBOO](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/bamboo/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?bamboo)

Pressing the button allows the player to pass through the bamboo and quickly cut through it by bouncing between the bamboos.

#### Other Special Mechanisms

[![CHARGE BEAM](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/chargebeam/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?chargebeam)

Charging energy, where managing the charge amount is crucial for the game to be meaningful.

[![LASER FORTRESS](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/laserfortress/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?laserfortress)

Sweeping away, a super-powered variant of firing shots. Mixing enemies and allies ensures that overpowered attacks can backfire.

[![SHINY](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/shiny/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?shiny)

Rain or shine, where rain accelerates human movement, enabling quicker evacuation to the right end. This peculiar mechanic doesn't seem easily transferable to other games.

### Combining Multiple Actions

Combining the above actions is a classic approach.

[![SCRAMBIRD](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/scrambird/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?scrambird)

Flapping + Shooting,

[![TILTED](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/tilted/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?tilted)

Multi-jump + Reversing direction,

[![UP SHOT](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/upshot/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?upshot)

Shooting + Stopping.

Additionally, an action can have multiple effects in the game.

[![BOMB UP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/bombup/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?bombup)

For instance, dropping/exploding a bomb with the button, with the explosion also launching the player. Adjusting the explosion and player positions allows control over player movement. This method can realize quite complex actions with one button, but too much complexity can render control difficult, hence moderation is crucial.

### Combining Rotational Movement

Similar to angle adjustment, but here the player or cannon is always rotating, and timing the jumps or shots is crucial.

[![ORBIT MAN](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/orbitman/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?orbitman)

With the direction of the jump rotating, players must time their jumps toward stars precisely.

[![ARCFIRE](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/arcfire/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?arcfire)

As the cannon rotates, players must time their shots precisely when facing enemies. This game allows for range and attack area adjustments by holding down the button, and a slight advance in the shooting direction, enabling various actions with one button.

### Utilizing Terrain

If input variation is challenging, changing the player's actions based on the terrain they are on is a viable solution.

[![TURBULENT](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/turbulent/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?turbulent)

Even for a simple action like jumping, altering the jumping terrain to a rough sea surface can change the jump direction based on timing.

[![SUB JUMP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/subjump/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?subjump)

Dividing the screen into underwater and above water, where button press causes ascension underwater and jumping above water, assigns multiple roles to the button based on terrain.

### Utilizing Items

Besides terrain, item utilization is another method. Picking up an item changes some mode, with the choice to pick up or ignore the item substituting for input variety.

[![MIRROR FLOOR](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/mirrorfloor/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?mirrorfloor)

Coins switch the direction of gravity; players must observe the next floor's position to decide whether to collect the coins, which impacts their ability to hop onto the next floor.

[![LIFT UP](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/liftup/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?liftup)

Collecting items alters the direction of movement. Skillfully collecting reversal items while gathering coins, before hitting left or right spikes is necessary.

[![REBIRTH](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/rebirth/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?rebirth)

Getting hit by a truck transports players to a reversed world. Whether the truck counts as an item is debatable, but players need to decide to get hit or not based on the next diamond's position.

[![R WHEEL](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/rwheel/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?rwheel)

Collecting items fires lasers downward, destroying spike obstacles. This game also spawns lasers downward when jumping, with spikes circling back to the player, and items appearing when jumping. Multiple events are triggered by the jump action in this game.

### Conclusion

Contrary to the assumption that one-button games cannot offer much action variation, the examples listed here prove that a wide array of game types can be created. By leveraging the potential of one-button games, I am eager to develop a variety of games in the future.

Although the simplicity of one-button games is an advantage, it also poses unexpected pitfalls. For instance, a game may unintentionally evolve into a repetitive button-mashing or continuous button-holding pattern where players can earn endless points. Therefore, it's imperative to test for such repetitive play patterns to ensure a well-balanced and engaging gameplay experience.

Lastly, it's important to remember that being a one-button game and being an enjoyable game are unrelated. Thus, it's vital to ensure the game is fun, has a sense of exhilaration and tension, well-balanced risk and reward, among other aspects of enjoyable gaming experience. Then, consider how to encapsulate that enjoyment within the one-button game format.
