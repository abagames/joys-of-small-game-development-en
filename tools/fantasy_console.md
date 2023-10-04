## Creating a Fantasy Console

A fantasy console [^1] embodies a developer's whimsical thought of, "It would be fun if there was such a game console." It's about envisaging non-existent versions of Game Boy systems or Famicoms, implementing them on a PC, and enjoying the result—that's what a fantasy console is.

The quintessential example of a fantasy console is undoubtedly PICO-8.[^2] With a screen of 128x128 pixels, simultaneous playback of four sounds, 256 sprites of 8x8 pixels each, and a rich machine inclusive of a Lua development environment, pixel art editor, music editor, and map editor, it's an innovative piece of tech.

Despite the term "console",[^3] many fantasy consoles encompass a development environment within their build. They tend to bear resemblances to microcomputers like the MSX or Family BASIC.

Creating a fantasy console at the level of PICO-8 is quite a challenge. However, the aspiration to craft one's own fantasy console is enticing. This necessitates deliberately limiting the specifications. Aiming for a fantasy console with a very small screen, simple sound output, and basic input means led to my creation of PEEKPOKE.[^4]

PEEKPOKE is playable on PC and smartphone browsers (playable with a screen click).

[![BOMB SNAKE](https://raw.githubusercontent.com/abagames/peekpoke/main/docs/screenshot.gif)](https://abagames.github.io/peekpoke/bombsnake/)

It's a snake game where you maneuver the snake to collect red bombs using the arrow keys (up, down, left, right) or WASD keys. On smartphones, control is facilitated by a virtual pad at the bottom of the screen.

![PEEKPOKE memory map](https://raw.githubusercontent.com/abagames/peekpoke/main/docs/memorymap.png)

In PEEKPOKE, machine control is solely managed through the peek and poke commands for reading and writing to memory. It employs memory-mapped I/O [^5] to operate a limited feature set: a 32x30 pixel 8-color screen, an 8x5 text screen, seven key inputs, and a single-tone buzzer. There is no built-in development environment; games can be scripted in JavaScript.[^6]

By relegating all the console-specific features to memory and offloading the development environment to JavaScript, the construction process was significantly simplified. The games that can be created are fairly basic, yet it can just about qualify as a fantasy console. Adding a splash screen on startup adds a touch of a fantasy console aesthetic.

Without the development environment, the effort to create a fantasy console is considerably reduced. Fantasizing about a console with intriguing specs and creating one effortlessly is quite enjoyable. The architecture of the console created this time is fairly straightforward. However, it would be fun to consider designing consoles with more exotic features, or those paying homage to existing consoles like Cassette Vision or ATARI 2600.

---

[^1]: [Fantasy video game console](https://en.wikipedia.org/wiki/Fantasy_video_game_console)
[^2]: [PICO-8](https://www.lexaloffle.com/pico-8.php)
[^3]: [Video game console](https://en.wikipedia.org/wiki/Video_game_console)
[^4]: [PEEKPOKE](https://github.com/abagames/peekpoke)
[^5]: [Memory-mapped I/O and port-mapped I/O](https://en.wikipedia.org/wiki/Memory-mapped_I/O_and_port-mapped_I/O)
[^6]: [peekpoke bombsnake/main.js](https://github.com/abagames/peekpoke/blob/main/docs/bombsnake/main.js)
