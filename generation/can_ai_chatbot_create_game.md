## Can AI Chatbots Create New Games?

AI chatbots equipped with Large Language Models (LLMs) are capable of generating game ideas and implementing code. However, their abilities are still in development, and they cannot yet create well-balanced games without human intervention. Nevertheless, recent improvements in LLM performance have enabled them to handle many aspects of small game development.

### The GPT-3.5 Era

GPT-4 became available on ChatGPT on March 14, 2023, and prior to that, GPT-3.5 was in use. While GPT-3.5 was a groundbreaking LLM at its launch, it's undeniable that the quality of its output falls short when compared to more recent, higher-performance LLMs.

Game development using GPT-3.5 faced the following challenges:

- Difficulty in conceiving new game ideas detailed enough to be implementable at the algorithm level
- Inability to effectively implement source code for novel algorithms

When asked to generate mini-game ideas, GPT-3.5 would only return vague, generic concepts lacking the specificity required for implementation. Moreover, even when presented with concrete ideas, it struggled to produce appropriate code if new algorithms were needed. Consequently, utilizing LLMs as mini-game generators was challenging.

### The Claude 3.5 Sonnet Era

OpenAI progressively updated ChatGPT's model from GPT-3.5 to GPT-4 and GPT-4o, significantly improving its performance. Anthropic, OpenAI's competitor, also updated its Claude LLM, releasing Claude 3.5 Sonnet [^1] on June 21, 2024.

Along with these LLM performance improvements came the ability to attach large reference documents to prompts, allowing LLMs to work with various prerequisite knowledge. These enhancements in LLM performance and functionality have helped overcome the aforementioned issues to some extent.

### LLMs Are Becoming Better at Generating New Ideas

It's unclear whether LLM performance improvements directly correlate with enhanced idea generation capabilities. But there seems to be a perceptible improvement. Additionally, it has become easier to provide LLMs with prerequisite knowledge about ideation methods and examples of desired ideas through reference documents.

When using LLMs to automatically generate one-button action mini-games, "ideas" in this context refer to novel and interesting game rules. To facilitate this, I provided the LLM with the following knowledge:

- Brainstorming methods for generating game ideas [^2]
- Descriptions of actions that can be assigned to a single button [^3]
- Rules of existing self-made games [^4]

As a result, combined with the high performance of Claude 3.5 Sonnet, we were able to increase the probability of generating unique game rules.

### LLMs Can Implement New Algorithms When Following a Step-by-Step Process

As described above, LLMs have become capable of generating appropriate game rules. The next challenge is translating these rules into correct code.

Converting game rules directly into code remains difficult even for recent high-performance LLMs. The likelihood of obtaining correct code increases when gradually detailing the implementation methods from the game rules. Therefore, I instructed the LLM to implement the game using the following steps in the prompt:

1. Organize the game rules in terms of game environment, core mechanics, player interaction, and challenges.
2. Detail the behavior of game objects that realize the organized game rules, considering properties, initial states, shapes, colors, movements, and one-button controls.
3. Present a JavaScript skeleton code that implements the game rules and objects.
4. Complete the skeleton code into a playable game using libraries.

I also provided examples of implementing self-made games using these steps in the prompt. This approach helped communicate our expectations to the LLM and further improved its output.

### LLMs Struggle with Game Balance Adjustment

High-performance LLMs can now create game motifs, rules, and corresponding source code with a certain level of quality. But they still struggle with evaluating the quality of the created games and improving their shortcomings.

Here, the quality of a game refers to the following aspects:

- Does it function as a game? Are there any unreasonable game-over conditions or perpetual patterns?
- Does it have appropriate risks and rewards? Do scores and play time increase according to the player's skill?
- Is it fun? Is the gameplay intuitive and provides a sense of exhilaration?

Examples of improvements for these issues could include:

- Rule refinement: Modifying game-over conditions or scoring systems
- Parameter adjustment: Changing the speed or frequency of player character and enemy appearances
- Control method improvement: Modifying controls to be more intuitive and less stressful for players

It seems unlikely that LLMs alone can handle these tasks. To judge the quality of a created game, a computer would need to play the implemented game itself and analyze the results. While AI that can play games already exists beyond the scope of LLMs, it's unclear to what extent computers can understand human sensations like exhilaration.

Having a computer improve the weak points of a game appears to be very challenging. If AI could judge the quality of a game, it might be possible to use a reinforcement learning-like mechanism with that as a reward. However, it's questionable whether AI can appropriately improve rules and control methods or adjust the wide variety of in-game parameters to enhance the game.

Therefore, the scope of the use of LLMs in small game creation seems better limited to what LLMs can currently do well. This means that LLMs are only expected to create the game idea and generate the implementation code. The resulting code and games are still imperfect, so the following tasks are done manually:

- Fixing code bugs and rules that don't work as intended
- Improving rules and code to make the game viable
- Adding game-over conditions and scoring systems that consider risks and rewards
- Adjusting rules and parameters to make the game more enjoyable
- Implementing difficulty progression and adjusting the difficulty curve

Considering this, it might seem that using LLMs doesn't significantly reduce the workload. However, the code implemented by LLMs occasionally produces interesting behaviors. Therefore, it can still be useful for creating "toys" that serve as the basis for game ideas.

### Generative Reroll Game Development Using LLMs

By using LLMs in this way, it becomes possible to repeatedly generate games until one that suits your preferences is created, and then manually complete it. Let's call this process "Generative Reroll Game Development."

Here's an example of Generative Reroll Game Development. We used Claude 3.5 Sonnet as the LLM, with prompts and prerequisite knowledge stored in the repository [^5].

When given the theme "fragile pillars," the prompt suggests the following game:

> Pillar Paraglider: Control a paraglider flying through a course of fragile pillars. The paraglider constantly descends. Press the button to ascend, but each press also sends a shockwave that can damage nearby pillars. Core mechanic: Balancing ascent with pillar preservation.

After detailing and implementing this idea, we created the game [^6]. This is the direct output from Claude.

Pressing the button causes the red player character to ascend while simultaneously emitting a circular shockwave. The shockwave destroys the pillars. While it seems overly influenced by Flappy Bird, the behavior implemented is quite interesting.

However, this game has several obvious issues:

- It's too easy. Repeatedly pressing the button allows players to neutralize pillars with shockwaves. There's no game over even if the player character reaches the top or bottom of the screen.
- The scoring system is simplistic. The score is based solely on distance traveled, so risky actions don't lead to higher scores.
- It doesn't realize the original core mechanism. The intention was to balance ascent with pillar preservation, but it's not implemented that way. Moreover, faithfully implementing this mechanism might result in a stressful game with large hit detection for shockwaves.

In Generative Reroll Game Development, the crucial process is how to improve these games with interesting behaviors into genuinely enjoyable games.

For this game, I made the following changes:

- The circular shockwave affecting all directions was too powerful, so I added directionality to the player character, limiting the shockwave to a narrow angle in front of it. Also, the shockwave now only destroys the parts of pillars it directly hits, rather than entire pillars. I also implemented game over conditions when the player character touches the top or bottom of the screen.
- I awarded points for each destroyed part of a pillar. I also implemented a score multiplier for consecutive destructions, incentivizing risky behavior of flying towards pillars for higher scores.
- I disregarded the original core mechanism. Generally, a game about "destroying" is more fun than one about "avoiding destruction."

The resulting game can be seen in [^7].

![WAVY BIRD screenshot](https://abagames.github.io/claude-one-button-game-creation/wavybird/screenshot.gif)

The game evolved into one where you create holes in pillars with shockwaves to progress. While it might be slightly too difficult, it achieves a better balance of risk and reward than the initial version, resulting in a more complete game.

The differences between the improved version and the original code are detailed in [^8]. While it might seem that little of the original code remains, the original framework served as a useful reference for modifications, making it much easier than starting from scratch.

The completed version with sound and a title is available at [^9]. The repository [^5] contains numerous games developed through a similar process for reference.

This is the current state of Generative Reroll Game Development using LLMs. Whether this process is easier than a person coming up with ideas and implementing them conventionally is debatable. However, the development process of selecting games proposed by LLMs and figuring out how to make them interesting presents a different kind of enjoyment compared to traditional development processes. It's also important in Generative Reroll Game Development to enjoy the parallel processes of game development and prompt development/improvement for generation.

In the future, we might be able to simply tell an LLM "create an interesting game," and it will return a well-implemented game. Currently, it's common to need dozens of "rerolls" to get a game with interesting behavior, and the success rate is quite low. However, with previous LLMs, it was virtually impossible to get anything interesting returned, and generic, uninspired games were the norm. The fact that we can now generate something that feels at least somewhat novel, thanks to LLM evolution over the past year or so, is a positive sign.

If LLMs continue to evolve at this pace, the quality of ideas will improve, and they'll be able to implement these ideas more accurately in code. Moreover, when we point out issues like those mentioned above, LLMs might be able to modify the code accordingly. This could lead to playable games with fewer rerolls and simpler improvements. However, it's unclear at this point whether future LLMs will steadily improve in performance to achieve such capabilities. As of 2024, there's an impression that the rate of LLM performance improvement is slowing down.

### The Future of Game Development Utilizing AI Chatbots

Game development utilizing AI chatbots is not yet a fully automated process, but it holds new possibilities. Currently, AI chatbots have the ability to generate "toys" with interesting behaviors, and the effective process is for humans to refine these into complete games.

In the future, if LLM performance continues to improve, there's potential for generating higher quality game ideas and code. However, aspects like game balance adjustment and fun factor evaluation – the creative aspects – will likely still require human intervention for the foreseeable future.

"Generative Reroll Game Development" offers a new and different way to enjoy game development. The process of building games based on LLM-generated ideas and code, combined with human creativity, brings new discoveries and surprises.

As LLMs evolve, we can expect these development methods to advance further. For small game developers, AI chatbots hold the potential to open new doors of creativity.

---

[^1]: [Claude 3.5 Sonnet](https://www.anthropic.com/news/claude-3-5-sonnet)
[^2]: [claude-one-button-game-creation/ideas.md](https://github.com/abagames/claude-one-button-game-creation/blob/main/project_knowledge/ideas.md)
[^3]: [claude-one-button-game-creation/one_button.md](https://github.com/abagames/claude-one-button-game-creation/blob/main/project_knowledge/one_button.md)
[^4]: [claude-one-button-game-creation/arcfire.md](https://github.com/abagames/claude-one-button-game-creation/blob/main/project_knowledge/arcfire.md)
[^5]: [claude-one-button-game-creation](https://github.com/abagames/claude-one-button-game-creation/)
[^6]: [Claude's original Pillar Paraglider](https://abagames.github.io/claude-one-button-game-creation/?sample_before)
[^7]: [Improved Pillar Paraglider](https://abagames.github.io/claude-one-button-game-creation/?sample_after)
[^8]: [Improved and original diff](https://github.com/abagames/claude-one-button-game-creation/commit/9e04ca08aa426f33909e99b6eb5d19d6ec55e446)
[^9]: [Pillar Paraglider modified as WAVY BIRD](https://abagames.github.io/claude-one-button-game-creation/?wavybird)
