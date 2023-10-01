## Automatic Level Generation for Puzzle Games

In this section, let's explore automatic level generation, or in other words, the automatic generation of puzzle patterns. While games like Game & Watch are played on a single screen, many games have multiple levels or terrains that appear as you scroll, necessitating the generation of levels.

The quality of level creation directly impacts the gameplay, especially in puzzle games. Particularly in non-action puzzle games like Sokoban,[^1] it's crucial to create levels that are enjoyable to solve.

Various level generators for Sokoban already exist. The typical method of creation includes:

1. Creating an empty room where no boxes are placed.
2. Placing boxes in the correct positions.
3. Simulating the game in reverse to distribute the boxes around.

The third step essentially ensures that if a player were to "pull" and shift the boxes, the boxes can indeed be moved to their correct positions.

When examining an implementation of a generator based on the above method,[^2] if a player gets stuck, it backtracks to search for other arrangements. A paper on the generation method [^3] introduced metrics such as the number of times a player pushes a box in a straight line or goes to push another box, with the aim of creating levels where boxes are placed as far from the correct positions as possible, thereby increasing the tasks a player must perform.

There's also a paper aiming to generate levels for any puzzle created [^4] using the universal puzzle game creation language known as PuzzleScript.[^5] By passing the characteristics of game objects from the PuzzleScript rule analyzer to the level generator and evaluator, levels are created. This approach, where the evaluator determines whether a generated level is solvable or enjoyable, differs from the aforementioned reverse simulation method.

While existing approaches are diverse, let’s attempt level generation for our custom puzzle game.

I attempted to create a puzzle game, slickslack,[^6] reminiscent of a mix between Sokoban and Pengo.[^7] The objective of the game, displayed by a blue square, is to flick boxes to slip them into yellow correct positions (click the image to play).

[![slickslack_screenshot](https://abagames.github.io/slickslack/screenshot.gif)](https://abagames.github.io/slickslack/index.html)

The level auto-generation method adopted is similar to other Sokoban generators, simulating the game in reverse from the correct answers. However, rather than creating an empty room initially, a room entirely of walls is created, and while slipping the boxes in reverse, walls are excavated.

![slickslack_screenshot_generating](https://abagames.github.io/slickslack/screenshot_generating.gif)

1. Create a room of arbitrary size consisting entirely of walls (or spaces that can either be walls or empty).
2. Place boxes in correct positions.
3. Slip boxes in arbitrary directions for arbitrary distances.
4. Place walls opposite to the slipping direction at the start of the slip to ensure boxes stop there.
5. Confirm the slipped area as empty (excavate the wall).

Perform the above slipping action for an arbitrary number of times to create a level. However, creating levels this way without consideration doesn’t guarantee enjoyable levels, so some tweaking is done.

Since this puzzle lacks a player character, boxes can be slipped quite freely. Therefore, to achieve a puzzling feel, the order of slipping boxes, or how to stop boxes at the right places by hitting other boxes, and interactions between boxes need to be considered. Also, too many walls reduce the gameplay constraints, diminishing the puzzle-like feel. Considering these, the following tweaks were made:

- Prefer directions that allow boxes to be stopped by existing walls or other boxes when slipping, avoiding creating new walls.
- Aim to position boxes adjacent to other boxes after slipping.

I also created another auto-generating level puzzle game named HAKOSAN.[^8] The goal is to slide three characters simultaneously using the arrow keys to reach the red destination (click the image to play).

<a href="https://abagames.github.io/hakosan/build/"><img src="https://raw.githubusercontent.com/abagames/hakosan/main/docs/screenshot.gif" alt="HAKOSAN" width="640"/></a>

Similarly, levels are generated by reversing the characters' slides from the destination.

Thus, this method of auto-generating problems by reversing the puzzle from the correct answer proves to be applicable in many scenarios. Adding an evaluator like the one mentioned in the PuzzleScript paper, to determine the fun factor of generated levels and select them, could enhance this method. This paper evaluates levels using various metrics: the distance between boxes and correct positions, the number of player moves, the number of applied rules, and so on. While there's no certainty that these metrics accurately reflect the enjoyment of solving the levels, they seem useful for filtering out clearly unenjoyable levels. With adequate resources, incorporating such refinements could lead to improved level generation.

---

[^1]: [Sokoban](https://en.wikipedia.org/wiki/Sokoban)
[^2]: [sokoban](https://github.com/miki151/sokoban)
[^3]: [Procedural Generation of Sokoban Levels (pdf)](https://ianparberry.com/pubs/GAMEON-NA_METH_03.pdf)
[^4]: [Automatic Puzzle Level Generation: A General Approach using a Description Language (pdf)](https://www.um.edu.mt/library/oar/bitstream/123456789/81990/1/Automatic_puzzle_level_generation_a_general_approach_using_a_description_language_2015.pdf)
[^5]: [PuzzleScript](http://www.puzzlescript.net/)
[^6]: [slickslack](https://github.com/abagames/slickslack)
[^7]: [Pengo (video game)](https://en.wikipedia.org/wiki/Pengo_%28video_game%29)
[^8]: [hakosan](https://github.com/abagames/hakosan)