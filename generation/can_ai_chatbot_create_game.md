## Can AI Chatbots Create New Games?

While there are several methods to conceive game ideas using ChatGPT, getting it to think up and implement a new game is challenging. At least the current version of ChatGPT presents the following issues:

- It's difficult to get ChatGPT to come up with new game ideas detailed enough to be implemented.
- ChatGPT tends to struggle with implementing new, unprecedented algorithms into source code.

### It's Hard to Get ChatGPT to Think Up New Game Ideas

ChatGPT typically provides straightforward answers to given questions. When asked for new action mini-game ideas, it tends to return bland, mundane ideas (as demonstrated below with an example using GPT-3.5. Note that GPT models continuously improve, so different results might be obtained).

> I want you to act as a game designer. Show me ideas for new action mini-games.

The response to this prompt was rather vague, providing generic game ideas like:

> Certainly! Here are some ideas for action mini-games that could be integrated into a larger video game or used as standalone experiences:
>
> Laser Maze Runner:
>
> The player navigates through a complex maze filled with laser beams. They must use their agility and quick reflexes to dodge and jump over the lasers to reach the exit.

With the following prompt, one might attempt to derive more detailed algorithms by requesting pseudocode for a game:

> I want you to act as a game programmer. Write a pseudo code outlining the detailed algorithm representing the rules of the following game:
>
> Game 2: Pinball Panic
>
> Selected tags: player: circle, weapon: bounce, field: pins, on pressed: shoot
>
> Description: In this game, the player controls a circular character that bounces around a pinball-like field. The player can shoot projectiles by pressing the button, which bounce off the pins and destroy enemies. The objective is to survive as long as possible while racking up points by destroying enemies and collecting power-ups.

However, the generated code lacks specificity and falls short of being suitable for implementation.

### ChatGPT Struggles to Implement New Algorithms

Another issue is that while ChatGPT is adept at implementing existing algorithms in various programming languages, it falls short when asked to code novel algorithms.

In the article "Can GPT-4 Actually Write Code?",[^1] an attempt was made to get ChatGPT to write an algorithm to find a path that avoids fire as much as possible. While ChatGPT easily generates code for a generic A\* search algorithm, it falters when asked to adjust it to the specific request.

ChatGPT excels at interpreting user requests to retrieve existing code or amend code based on additional requirements. However, its ability to generate code for previously non-existent algorithms or rules is uncertain.

For instance, an attempt was made to get ChatGPT to code a simple, novel game called PIN CLIMB.

[![PIN CLIMB](https://github.com/abagames/crisp-game-lib-games/raw/main/docs/pinclimb/screenshot.gif)](https://abagames.github.io/crisp-game-lib-games/?pinclimb)

Based on a text describing the game's implementation, pseudocode for the game's algorithm was requested using the following prompt:

<blockquote>
<p>
I want you to act as a game programmer. Write a pseudo code outlining the detailed algorithm for the following game inside one unique code block. Do not write explanations.<br>
# Characters<br>
- bar<br>
- pins<br>
# Controls<br>
- The bar stretches as long as the button is held down and shrinks to a default length when the button is released.<br>
# Rules<br>
- One end of the bar is fixed to the pin and the other end rotates around the pin.<br>
- The game screen scrolls down so that the bar is positioned slightly above the bottom edge of the screen.<br>
- Pins appear at random locations at the top edge of the screen after each scrolling of a certain distance.<br>
- When the bar catches on another pin, the bar is fixed to that pin.<br>
# Initial state<br>
- Pins are placed in about 10 random positions on the screen, and the bar is fixed to the bottom pin.
</p>
</blockquote>

Subsequently, an attempt was made to transform this into specific Phaser source code:

> Implement the game using the HTML5 game framework "Phaser 3" without using external resources such as image files or audio files. Just show me the JavaScript source code.

The attempt was unsuccessful. Even when providing step-by-step instructions to write direct source code—for instance, drawing pins, scrolling, and rotating the string—the process stumbled when it came to fixing the string to a new pin upon contact.

### Can These Challenges be Overcome with Clever Prompting?

It's unclear.

Conceiving game ideas freely and translating them into rules or implementations specifically seems quite challenging to manage through prompting. Besides, the model's limitations may not be overcome just by crafting prompts.

### Will Future GPT-oo Solve These Issues?

It's unclear.

Given the rapid advancements in image generation AI, these issues might be resolved in about six months. Whether these challenges are surmountable with larger models or if the approach is fundamentally flawed remains to be seen at this point.

In fact, when the initial action mini-game idea was posed to GPT-4 instead of GPT-3.5, a slightly improved response was received:

> Certainly! Here are some unique action mini-game ideas:
>
> Asteroid Surfing
>
> Setting: Outer space, amidst a field of rapidly moving asteroids.<br>
> Objective: Ride the largest asteroids and jump between them to reach a goal point in the least amount of time.<br>
> Mechanics: Players must balance on moving asteroids, time their jumps, and avoid smaller, more hazardous space debris.

Though the game idea is still mundane, more detailed game content is obtained. The development of language models, coupled with clever prompting, might pave the way for more exciting and specific game ideas.

### Are There Other Approaches That Could Work Now?

It's unclear.

Starting with the code of existing games like Pong or Breakout, and iteratively adding new elements through a dialog might work well. This approach would require prompt engineering to determine how much novelty is acceptable and how detailed instructions should be for efficiency.

When asked whether creating a game this way is more efficient compared to writing code directly, the answer is likely no. Therefore, the pursuit is not about efficiency, but about the fun of the challenge—creating a game using ChatGPT. It might be enjoyable to explore various methods of creating a "game to make a game with AI" while the topic remains fresh.

---

[^1]: [Can GPT-4 _Actually_ Write Code?](https://tylerglaiel.substack.com/p/can-gpt-4-actually-write-code)
