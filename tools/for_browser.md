## Creating a Library for Small Browser Games

What features should be included in game libraries or game engines? An article titled "How to make your own game engine (and why)" [^1] lists the following features:

- Basic Features:
  - System Initialization: Preparing windows, initiating rendering, and audio systems.
  - Frame Timing Control: Update processing called regularly at intervals of 1/60 seconds.
  - Input: Handling button inputs, etc.
  - Rendering: Drawing 2D or 3D textures, models, etc.
  - Arithmetic Utilities: Vector operations and other game-required functions.
- Advanced Features:
  - Game Object & Scene Management: Managing multiple objects and transitioning between multiple scenes.
  - Audio: Audio playback using audio frameworks.
  - File Management: Managing files and resources.
  - Networking: Communication features for multiplayer games.

Additionally, collision detection, physics calculations, serialization, animation, UI, etc., are mentioned, although they are not essential. Existing game engines offer feature sets backed by years of experience, and understanding their functionalities can be very beneficial when creating one's own game library or engine.

The article also outlines the mindset to have when creating a custom game engine:

- Build the engine and game simultaneously: The features that the engine should have are backed by the needs of the game you want to create.
- Don't create features until they are needed: Avoid over-engineering features not required for your game.
- Use a programming language you are comfortable with: Building an engine is a challenging task that should not be undertaken while learning a new programming language.
- Don't seek the right answer from the beginning: After going through the experience of building engines multiple times, you'll eventually create a usable engine.

<br>

So, what features should a game library aimed at small browser games have? The basic features mentioned above are necessary, but advanced features could have limited implementation. Also, if the goal is to quickly bring an idea to life, focusing on implementing the mechanics the game requires would be better.

With these considerations, I created a game library called crisp-game-lib.[^2] This library has the following features:

- Scenes like title, in-game, and game over are standardized within the library, eliminating the need for individual development for each game.
- Provides features particularly required for small games, like high-score management and replay.
- Constraints on resolution, color, and sound, reducing the need for time-consuming rich expressions.
- Making the game "juicy" is easy. Specifically, various visual and sound effects can be added easily.

In crisp-game-lib, by writing a single JavaScript file [^3] for the game's `title`, `description`, and an `update` function called 60 times per second, you can create browser games that work on both PC and mobile.

A unique feature not found in other libraries is the ability to render boxes, lines, arcs, text, and characters, with integrated collision detection.

[![ref_collision screenshot](https://abagames.github.io/crisp-game-lib-games/ref_collision/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?ref_collision)

When an element is drawn with the function, the return value will tell you if the element overlaps with other shapes, text, or characters already on the screen. Just by checking this value, collisions can be detected even with complex shapes like lines and arcs, without needing specific collision detection processing.

Additionally, the library has the following features to make the game juicy:

- Sound effects that can be played by simply selecting the desired sound name.[^4]
- Automatically generated BGM by setting the option [^5] `isPlayingBgm` to true.
- Replay functionality enabled by setting `isReplayEnabled` to true.
- Appearance-altering features, such as a retro CRT style or pixel art style, can be set by defining `theme`.
- Pixel art can be easily defined with the `characters` array.

Creating your own game library, with features trimmed down to suit your needs, can be an enjoyable way to develop games more efficiently. Consider what features would be desirable in a library that aligns with your game development style, and try creating your own original library.

---

[^1]: [How to make your own game engine (and why)](https://medium.com/geekculture/how-to-make-your-own-game-engine-and-why-ddf0acbc5f3)
[^2]: [crisp-game-lib](https://github.com/abagames/crisp-game-lib)
[^3]: [pinclimb main.js](https://github.com/abagames/crisp-game-lib/blob/master/docs/pinclimb/main.js)
[^4]: [crisp-game-lib sound demo](https://abagames.github.io/crisp-game-lib-games/?ref_sound)
[^5]: [crisp-game-lib / Options](https://abagames.github.io/crisp-game-lib/ref_document/types/Options.html)
