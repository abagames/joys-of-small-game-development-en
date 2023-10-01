## Developing Games for DIY Handheld Devices

Recently, there's a trend of creating DIY handheld gaming consoles using a single-board microcontroller such as Arduino [^1] as the core, and adding a display and buttons to it. The advantage is that you can create a gaming console according to your liking. However, the downside is the proliferation of various devices, which means there isn't a common device that many people own.

Games for these devices are often written in the C language. Therefore, it's necessary to implement the accompanying libraries in C as well.

This time, I ported my custom library, initially implemented in JavaScript (TypeScript) for browsers, to the C language. I have named it crisp-game-lib-portable.[^2]

![PyBadge crisp-game-lib-portable screenshot](https://abagames.github.io/crisp-game-lib-portable/screenshotPyBadge.gif)

Games created with crisp-game-lib-portable are compatible with devices like M5StickC PLUS [^3] and Adafruit PyBadge.[^4] Additionally, by utilizing Emscripten,[^5] they can now be played on browsers as well.

The library core [^6] and the game code [^7] are designed to be common for all devices including browsers, with the goal of requiring only a minimal amount of device-specific code.

The processes that need to be written in device-specific code include:

- Device initialization (e.g., `setup()` in Arduino) and calling `initGame()` from there.
- Frame update process (e.g., `loop()` in Arduino) with button state notification by calling `setButtonState()` and invoking `updateFrame()`.
- Drawing and sound-related processes defined in `machineDependent.h`.[^8]

With this approach, the device-specific implementations required for general devices amount to about 250 lines.

Accommodating this function might be somewhat cumbersome on devices like PyBadge, where only the buzzer volume can be adjusted using `analogWrite()`, necessitating manual management of sound timing and generation of square waves.

The `md_drawCharacter(unsigned char grid[CHARACTER_HEIGHT][CHARACTER_WIDTH][3], float x, float y, int hash)` function, which displays pixel art, also requires some effort. The last hash value is intended for caching the pattern definition of the pixel art rather than parsing and drawing it every time. If you are utilizing the LovyanGFX library [^9] for drawing, you should save the LGFX_Sprite and hash value as a pair, then retrieve and execute `pushSprite()`.

Writing code while considering such portability is a fun experience and is something that can't be done without targeting various devices with the library. Creating a unique gaming library, while utilizing common development environments like the Arduino IDE and multi-device compatible libraries like Adafruit Arcada [^10] or LovyanGFX, offers a unique experience. Working with a myriad of microcontroller boards presents a different kind of enjoyment compared to developing libraries targeting PCs or smartphones. If interested, I would encourage you to give it a try.

---

[^1]: [Arduino](https://en.wikipedia.org/wiki/Arduino)
[^2]: [crisp-game-lib-portable](https://github.com/abagames/crisp-game-lib-portable)
[^3]: [M5StickC PLUS](https://shop.m5stack.com/products/m5stickc-plus-esp32-pico-mini-iot-development-kit)
[^4]: [Adafruit PyBadge](https://learn.adafruit.com/adafruit-pybadge)
[^5]: [Emscripten](https://emscripten.org/)
[^6]: [crisp-game-lib-portable src/lib](https://github.com/abagames/crisp-game-lib-portable/tree/main/src/lib)
[^7]: [crisp-game-lib-portable src/games](https://github.com/abagames/crisp-game-lib-portable/tree/main/src/games)
[^8]: [machineDependent.h](https://github.com/abagames/crisp-game-lib-portable/blob/main/src/lib/machineDependent.h)
[^9]: [LovyanGFX](https://github.com/lovyan03/LovyanGFX)
[^10]: [Adafruit Arcada](https://github.com/adafruit/Adafruit_Arcada)
