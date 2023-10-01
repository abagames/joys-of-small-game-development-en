## Creating Puzzle Games with AI Chatbot

The article "ChatGPT invented its own puzzle game" [^1] discusses a scenario where ChatGPT was tasked with devising a new logic puzzle, which led to the proposal of a game named Sumplete. In this game, numbers are placed on a two-dimensional grid with the sum of the numbers in each row and column written on the right and bottom edges, respectively. Players cross out numbers on the grid to match the provided sums.

<img src="https://substackcdn.com/image/fetch/w_1456,c_limit,f_webp,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2Fdd3b6e61-fb2a-4f7f-a575-97fbbffb5008_1194x1482.png" alt="Sumplete" width="400"/>

However, this game turned out to already exist under the name Summer,[^2] designed for smartphones. It's impossible for both humans and AI to be aware of every game in existence, so creating a game that already exists is a common occurrence. Guaranteeing the novelty of a game is challenging.

Nonetheless, engaging ChatGPT in brainstorming new logic puzzles is an intriguing endeavor. For instance, when prompted with the following task, ChatGPT was able to propose several puzzles:

> I want you to act as a logic puzzle game designer. Devise 5 novel logic puzzles. Create rules that are different from logic puzzles that already exist, such as Sudoku. The puzzle should consist of a two-dimensional grid. Several grids may be divided by walls. The initial state of the cells consists of both cells containing numerals or symbols, as well as empty cells. The player fills in the blank squares and tries to reach the correct solution.

The prompt requested five logic puzzles involving a 2D grid, with some cells containing numbers or symbols, while others remain empty. The grids might be divided by walls. It's anticipated that puzzles resembling Heyawake [^3] would be suggested.

Among the proposals was a puzzle called "Magnet Blocks":

> In this puzzle, the grid contains magnets of opposite polarity (north and south). The player must fill in the grid with blocks of positive and negative polarity, such that each block attracts or repels adjacent magnets according to their polarities. A block can only be placed if it fits in with the surrounding magnets, and no two blocks of the same polarity can touch each other.

Magnet Blocks, themed around magnets, presents a set of rules that are somewhat vague. However, interpreting it as a game where magnets labeled N and N, S and S can't touch, an implementation was achieved (click image to play).

[![Magnet Blocks](https://raw.githubusercontent.com/abagames/crisp-game-lib-11-games/main/docs/magnetblocks/screenshot.gif)](https://abagames.github.io/crisp-game-lib-11-games/?magnetblocks)

Here are the specific rules:

- The grid initially contains bar magnets and walls.
- Bar magnets must be placed in empty cells such that N and N, S and S do not touch. Bar magnets can have any length of 3 cells or more.
- The puzzle is cleared when all empty cells have a bar magnet placed.

Despite the subpar level generation logic, which renders the puzzle lacking in depth, it still qualifies as a puzzle.

Is this puzzle truly novel? A similar game called Magnets [^4] exists, sharing the magnet theme but differing significantly in rules:

- Placement and orientation of bar magnets are predetermined, with a fixed length of 2.
- Constraints on the occurrence of + and - in each row and column are given on the grid's perimeter.
- Not all empty cells need to be filled.

Thus far, no puzzle with identical rules has been discovered. However, the possibility of a similar rule set in a non-magnet themed puzzle cannot be denied.

Logic puzzles often have established styles, making them a good motif for ChatGPT to brainstorm new rules around. However, due to these fixed styles, there's a high chance that what's thought to be new might align with existing games.

Moreover, it's challenging for ChatGPT to generate precise rules for a viable puzzle; this requires human intervention to refine vague proposals into concrete rules. Converting these into playable program code remains a hard task.

Determining whether the created puzzle is enjoyable to solve is another challenge, as it not only depends on the rules but also on the logic behind level generation.

By supplementing the tasks that ChatGPT struggles with, such as creating precise rules, with other methods, programs, or plugins, the applications of AI chatbots could be further expanded.

---

[^1]: [ChatGPT invented its own puzzle game.](https://puzzledpenguin.substack.com/p/chatgpt-invented-its-own-puzzle-game)
[^2]: [Summer](https://web.archive.org/web/20230726112930/https://play.google.com/store/apps/details?id=com.rohitpailwangames.summerpro)
[^3]: [Heyawake](https://www.nikoli.co.jp/en/puzzles/heyawake/)
[^4]: [Magnets](https://www.chiark.greenend.org.uk/~sgtatham/puzzles/js/magnets.html)
