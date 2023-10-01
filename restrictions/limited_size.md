## Creating Games within Limited Size Constraints

Game Jams often impose constraints on the size of game binaries or source code. Notable examples include the competition js13kGames,[^1] which challenges participants to create browser games within 13 kilobytes.

Attempts to achieve diverse expressions using short code span across many fields, not just gaming. For instance, using ggplot2,[^2] beautiful geometric patterns can be created within 280 characters.[^3] Additionally, collections of music and generative art have been created within 140 characters [^4] using SuperCollider [^5] and JavaScript on platforms like Dwitter.[^6]

The essence of compactly coded creations lies in the beauty of densely packed information. They embody the ingenuity of achieving maximum effects with minimal components.

On Dwitter, users share not only graphics and music, but games as well. For example, the game Crossy Tortoise [^7] involves navigating a tortoise across roads, exemplifying a one-button game realized within 140 characters. However, it lacks a scoring system, and the game concludes once the crossing is achieved.

To qualify as a game, the following elements are desirable:

- Presence of a scoring system.
- A game-over condition.
- Escalating difficulty.
- Preferably, sound effects.

Considering the inclusion of these elements, let’s ponder the plausible regulations for short code:

- Crafting a JavaScript update function for every frame, with a maximum length of 256 characters.
- Incorporating libraries like p5.js,[^8] Tone.js,[^9] and lodash.range [^10] for convenient functions suited for gaming.
- Assigning one-character aliases like M, X, Y, R, N, and A to p5.mouseIsPressed, p5.mouseX, p5.mouseY, p5.random(), Tone.synth.triggerAttackRelease(), and \_.range() respectively, to allow function calls within fewer characters.
- Variable S, representing the score, is displayed at the top, while variable T, representing the frame count since the game started, is utilized for difficulty adjustments.

Several sample games were created adhering to these regulations [^11] (click the image to play).

[![springcar](https://raw.githubusercontent.com/abagames/jsgame256/master/docs/springcar.png)](https://abagames.github.io/jsgame256/springcar.html)

One such game, springcar, involves a car that jumps upon clicking. The code is as follows:

```javascript
clear(),
  T || ((s = A(9).map((i) => [10 * i])), (y = v = 0)),
  (d = 1 + T / 999),
  s.map((u) => text("🔩", (u[0] = u[0] < 99 ? u[0] + d : -R(30)), 80)),
  (y += v += (M ? 0.1 : 0.2) * d),
  get(74, y)[3] + get(82, y)[3] > 0 && ((v = -1), (y = 72), S++, N(333, 0.1)),
  y > 70 && v < 1 && M && ((v = -3), N(444, 0.2)),
  y > 95 && ((S = y = T = 0), N(222, 0.5)),
  text("🚗", 75, y);
```

With these regulations, creating a game is still manageable. There are also Pong created under stricter regulations, such as not allowing the addition of libraries and including the entire HTML in 226 bytes.[^12] You can see many more excellent codes like this in codegolf JS.[^13]

Under these regulations, crafting a basic game within about an hour is feasible. However, the 256-character constraint is stringent, and attempting to implement intricate movements quickly exceeds the character limit. It’s disheartening when a game around 270 characters is crafted, and despite utilizing clever techniques, a reduction to meet the constraint necessitates downsizing the game system. Yet, without the 256-character constraint, there’s endless potential for adding effects and tweaking game balance. Thus, even if disheartening, abandoning these extras is part of the challenge.

The quick output achievable with size-constrained game development is intriguing. The notion that games can be crafted within such limited sizes implies that the rules and mechanics are significantly streamlined. Such constraints yield interesting games, serving as treasure troves of excellent ideas.

However, self-imposed size constraints often act more as shackles than as contributors to early completion, hence it's recommended only for those who find overcoming size constraints enjoyable. Numerous libraries and techniques exist for size compression.[^14] You can refer to these to gauge your interest and ascertain your aptitude, based on whether you find the concept amusing.

---

[^1]: [js13kGames](https://js13kgames.com/)
[^2]: [ggplot2](https://ggplot2.tidyverse.org/)
[^3]: [Tiny Art in Less Than 280 Characters](https://fronkonstin.com/2017/12/23/tiny-art-in-less-than-280-characters/)
[^4]: [sc140](https://archive.org/details/sc140)
[^5]: [SuperCollider](https://supercollider.github.io/)
[^6]: [Dwitter](https://www.dwitter.net/)
[^7]: [Crossy tortoise](https://www.dwitter.net/d/4671)
[^8]: [p5.js](https://p5js.org/)
[^9]: [Tone.js](https://tonejs.github.io/)
[^10]: [lodash.range](https://lodash.com/docs#range)
[^11]: [jsgame256](https://github.com/abagames/jsgame256)
[^12]: [PING - A Game in < 256 Bytes of HTML+JS](https://github.com/codegolf/ping)
[^13]: [codegolf JS](https://gist.github.com/xem/206db44adbdd09bac424)
[^14]: [js13kGames Resources](https://js13kgames.github.io/resources/)
