# Level 2: Navigation Speedrun

> You're in Normal mode. Your hands are on the keyboard.
> The question is: how do you get from where you are to where you need to be?
> Not with arrow keys. Not with the mouse. Faster than that.

---

## The Moves

| Motion | What it does                                              |
| ------ | --------------------------------------------------------- |
| `w`    | Jump forward one word                                     |
| `b`    | Jump backward one word                                    |
| `e`    | Jump to end of current word                               |
| `f<x>` | Jump to next occurrence of character `x` on this line     |
| `F<x>` | Jump to previous occurrence of character `x` on this line |
| `;`    | Repeat the last `f` or `F` jump                           |
| `0`    | Jump to start of line                                     |
| `$`    | Jump to end of line                                       |
| `gg`   | Jump to top of file                                       |
| `G`    | Jump to bottom of file                                    |

---

## The Multiplier

Here's where it gets good.

Every motion accepts a number prefix. That number repeats the motion.

| What you type | What happens                          |
| ------------- | ------------------------------------- |
| `5w`          | Jump forward 5 words                  |
| `3b`          | Jump backward 3 words                 |
| `10j`         | Move down 10 lines                    |
| `7k`          | Move up 7 lines                       |
| `4e`          | Jump to the end of the 4th word ahead |

You're not pressing `w` five times. You're pressing `5w` once.
This is the min-max. A single input that scales.

---

## Quest Log Entry #001

Mayor Lewis is reviewing the town calendar before the next council meeting.
He needs three facts:

1. The Spring festival winner
2. The total rainy days in Summer
3. The council note at the bottom.

Open the file: `nvim town-calendar.txt`

<!-- TODO: Press `G` to jump to the very last line of the calendar -->
<!-- TIP: G and gg are your anchors, use multipliers to cover the distance in between -->
<!-- TODO: Use `gg` then `10j` to step down into the Spring section -->
<!-- TIP: Don't stress about the exact count; overshoot and correct with k -->
<!-- TODO: Use `3w` to skip across a dense event line word by word -->
<!-- TODO: Use `10j` / `10k` to jump between seasons without counting rows -->
<!-- TIP: Multipliers feel slow to type at first, but 10j beats pressing j ten times -->

---

## Quest Log Entry #002

Willy keeps his catch log in one long file, every fish crammed onto a single line.
He needs you to look up three entries before he talks to Gus:

1. What did he sell to Gus, and what grade was it?
2. What was his best catch of the year, and where was it caught?
3. What note did he leave on the Tiger Trout?

These lines are dense. `w` and `b` for words, `f` to jump to a character, `0` and `$` to snap to the ends.

Open the file: `nvim willy-catch-log.txt`

<!-- TODO: Use `f|` to jump forward to the next field separator on a line, use `;` to repeat -->
<!-- TIP: `;` replays the last f/F jump, so f| then ;;; hops across all the separators -->
<!-- TODO: Use `F|` to jump back to the previous separator -->
<!-- TODO: Use `f:` to land on a field label's colon and then `w` to jump to its value -->
<!-- TIP: w after f: skips the colon and lands you on the value -->
<!-- TODO: Use `0` to snap back to the start of any line -->
<!-- TODO: Use `$` to jump to the end and check the notes field -->
<!-- TODO: Use `3w` or `2b` to skip multiple words at once on a crowded line -->

---

## Checkpoint

_Check the boxes with `r` (replace) `x`_

- [ ] Used `gg` and `G` to jump to top/bottom of the file
- [ ] Used a numeric multiplier like `10j` or `5w`
- [ ] Used `f<x>` to jump to a specific character on a line
- [ ] Used `F<x>` to jump backward to a character
- [ ] Used `;` to repeat character jump
- [ ] Used `0` and `$` to snap to line start/end
- [ ] Did not touch the arrow keys or mouse

> Open the next level: `cd ../03-combos` → [03-combos on GitLab](../03-combos)
