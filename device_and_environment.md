## Target Devices and Development Environment

When considering creating a small game, one of the first things to think about is the device it will run on - whether it's a PC, smartphone, or gaming console.

If you have no particular preference, creating a game for PC web browsers is recommended. Modern browsers have matured as platforms capable of running games developed in various development environments. It's also easy to get others to play your game; a simple announcement with a URL allows for seamless gameplay.

For those who enjoy the process of creating games, the choice of development environment, programming language, and game engine can stem from personal preference. This is not particularly dependent on the game's size; choose based on what you like. However, if you're targeting a small 2D game, engines like Unreal Engine [^1] may be overkill.

When creating for browsers, there are various development options available:

- JavaScript

Games running in browsers are written in JavaScript, making it a natural choice for game development. Utilizing libraries like p5.js [^2] or Phaser [^3] can ease tedious tasks such as rendering. With p5.js, beginners can start immediately by following along with the learning content [^4] or the reference [^5] using the web editor.[^6]

- Fantasy Consoles

Fantasy consoles are lightweight game engines encompassing game execution and development environments, including character, level, and sound editors. Examples include PICO-8,[^7] Pyxel,[^8] and TIC-80.[^9] These all-in-one environments, with deliberately limited functionality, are great for small game projects. They support different programming languages, so find one that suits your preference. If you want to try PICO-8, refer to the manual [^10] or API Reference [^11] while using the Education Edition.[^12]

- Game Engines

Many game engines like Unity,[^13] GameMaker,[^14] and Godot [^15] allow exporting games for browsers (HTML5), making it easy to play games created on the browser. They offer comprehensive asset management features, and the ability to release games not just on browsers but also on PC and mobile platforms, which are significant advantages.

- Maker Tools

If you want to create RPGs or visual novels, genre-specific tools are available. RPG Maker MV,[^16] for instance, is historically popular in this category, with tools traditionally called "makers." Besides RPG Maker, there are others like WOLF RPG Editor [^17] for RPGs, or TyranoBuilder Visual Novel Studio [^18] for visual novels. Many recent makers include browser export functionality.

- Visual Programming Languages

For those not accustomed to text-based programming, visual programming languages like Scratch [^19] or MakeCode [^20] are available. Although creating complex games can be challenging, they include pre-prepared graphics and sounds, making them suitable for smaller projects.

- Other Programming Languages

Modern browsers can run languages other than JavaScript, utilizing technologies like WebAssembly. [^21] However, the compilation process can be complicated, so it's easier to leverage fantasy consoles or game engines if possible. For example, use Pyxel for Python, or Unity for C#.

<br>

When creating for browsers, ensuring your game is operable with touch controls (or mouse controls on PC) allows for mobile compatibility, which is worth considering if you want to reach a wider audience.

The enjoyment derived from the game creation experience itself doesn't necessarily require a browser-oriented approach. Creating apps for PC or mobile, or using SmileBASIC 4 [^22] for Switch game creation, is also good. Games created with MakeCode can be played on your favorite handheld devices,[^23] with some individuals even running PICO-8 games on them.[^24] The motivation to create doesn't have to stem solely from the desire for ease of accessibility by many; it can also come from the intrigue of crafting for a particular device. Let's create freely.

---

[^1]: [Unreal Engine](https://www.unrealengine.com/en-US/)
[^2]: [p5.js](https://p5js.org/)
[^3]: [Phaser](https://phaser.io/)
[^4]: [learn | p5.js](https://p5js.org/learn/)
[^5]: [reference | p5.js](https://p5js.org/reference/)
[^6]: [p5.js web editor](https://editor.p5js.org/)
[^7]: [PICO-8](https://www.lexaloffle.com/pico-8.php)
[^8]: [Pyxel](https://github.com/kitao/pyxel/blob/main/README.md)
[^9]: [TIC-80](https://tic80.com/)
[^10]: [PICO-8 User Manual](https://www.lexaloffle.com/dl/docs/pico-8_manual.html)
[^11]: [APIReference | PICO-8 Wiki](https://pico-8.fandom.com/wiki/APIReference)
[^12]: [PICO-8 Education Edition](https://www.pico-8-edu.com/)
[^13]: [Unity](https://unity.com/en)
[^14]: [GameMaker](https://gamemaker.io/en)
[^15]: [Godot](https://godotengine.org/)
[^16]: [RPG Maker MV](https://store.steampowered.com/app/363890/RPG_Maker_MV/)
[^17]: [WOLF RPG Editor](https://widderune.wixsite.com/widderune/wolf-rpg-editor-english)
[^18]: [TyranoBuilder Visual Novel Studio](https://store.steampowered.com/app/345370/TyranoBuilder_Visual_Novel_Studio/)
[^19]: [Scratch](https://scratch.mit.edu/)
[^20]: [MakeCode](https://www.microsoft.com/en-US/makecode)
[^21]: [WebAssembly](https://developer.mozilla.org/en-US/docs/WebAssembly)
[^22]: [SmileBASIC 4](https://www.petc4.smilebasic.com/?lang=en)
[^23]: [MakeCode Hardware](https://arcade.makecode.com/hardware)
[^24]: [Simple handheld PICO-8 devices (summer 2021)](https://www.lexaloffle.com/bbs/?tid=44065)
