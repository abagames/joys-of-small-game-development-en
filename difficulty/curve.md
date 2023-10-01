## Rising Difficulty Curve

What does an appropriate escalation in difficulty entail, and at what pace should it occur? This largely depends on how long you want players to engage with a game. For instance, assuming a game should last 3 minutes, and you design it so that most players drop out when the difficulty doubles from the start, the following formula can be considered for calculating difficulty:

```
[Difficulty] = sqrt([Elapsed frame count] * 0.0001) + 1
```

Here, a 'frame' is a unit of time representing 1/60 of a second in the game. The elapsed frame count is 60 per second, and 3600 per minute. The term `sqrt` refers to the square root. Instead of making the difficulty linearly proportional to the frame count, using the sqrt function ensures a gentler rise in difficulty after a certain amount of time has passed. By inserting 10800, the frame count for 3 minutes, into the formula above, the resulting difficulty is 2.04, aligning with the initial assumption.

However, this difficulty setting may not suit all mini-games. In some cases, ramping up the difficulty more swiftly can create a more tense and engaging experience.

It’s hard to gauge what kind of difficulty escalation is appropriate without applying it to a game and observing the outcome. Hence, I visualized the rise in difficulty over time on a curve, prepared a UI to adjust this curve, and reflected it in a sample game (click the image to go to the demo page).

<a href="https://abagames.github.io/diffi-tween/"><img src="https://abagames.github.io/diffi-tween/screenshot.png" alt="diff-tween" width="600"/></a>

In the 'diff-tween' page, adjusting the difficulty curve on the right UI, then clicking on the left game screen starts a game where you dodge falling rocks. The initial curve setting is geared for a clear understanding of the difficulty escalation, doubling the difficulty in 30 seconds.

Each difficulty curve is defined by its formula (sqrt, linear, pow) and escalation rate (climb), and can be adjusted for a saw-tooth wave (saw) which drops the difficulty at fixed intervals. The saw-tooth wave is a good method to introduce variability in difficulty, a technique also used in Game & Watch. In addition, multiple parameters can be adjusted, such as rock falling speed (speed) and size

When there are multiple parameters affected by the difficulty, tuning becomes more challenging. Playing the game makes it apparent that, although players can manage the faster falling rocks (≒ game speed) with skill, it becomes impossible to cope once the rocks reach a certain size. It's conceivable to navigate around faster falling rocks, but larger rocks evoke an unavoidable and unfair impression.

Therefore, it's possible to use the sqrt function to escalate the size of the rocks, mitigating unfairness, while employing a linear increase for the rock fall speed from the game's outset to maintain tension, occasionally easing the pace with a saw-tooth wave.

Furthermore, such adjustments do have a downside as the initial difficulty might feel too easy and boring. In such cases, introducing mechanics like bonus points when passing close to rocks, encourages players to take risks in exchange for rewards, providing tension from the early stages of the game.
