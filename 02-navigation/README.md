# Level 2: Navigation Speedrun

> You're in Normal mode. Your hands are on the keyboard.
> The question is: how do you get from where you are to where you need to be?
> Not with arrow keys. Not with the mouse. Faster than that.

---

## The Moves

This is your reference, don't memorize it. The quests below walk you through the ones that matter.

| Motion    | What it does                                              |
| --------- | --------------------------------------------------------- |
| `w`       | Jump forward one word                                     |
| `b`       | Jump backward one word                                    |
| `e`       | Jump to end of current word                               |
| `f<x>`    | Jump to next occurrence of character `x` on this line     |
| `F<x>`    | Jump to previous occurrence of character `x` on this line |
| `;`       | Repeat the last `f` or `F` jump                           |
| `0`       | Jump to start of line                                     |
| `$`       | Jump to end of line                                       |
| `gg`      | Jump to top of file                                       |
| `G`       | Jump to bottom of file                                    |
| `/word`   | Search forward for `word`; `n` next match, `N` previous   |
| `*`       | Search for the word under your cursor                     |
| `{` / `}` | Jump backward / forward by blank lines                    |
| `%`       | Jump to matching bracket, paren, or brace                 |

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
This is the min-max. One decision, one action, same result.
Every motion accepts a multiplier. You're not fighting the editor to get somewhere, you're operating it.

---

## Quest Log Entry #001

Mayor Lewis is reviewing the town calendar before the next council meeting.
He needs three facts:

1. Who won the Spring festival?
2. How many rainy days were there in Summer?
3. What does the council note at the bottom say?

Open the file: `nvim town-calendar.txt`

> **TODO:** Press `G`, jump straight to the bottom and read the council note (fact #3)
>
> **TIP:** `G` and `gg` are your anchors. Use them first to orient, then navigate from there.
>
> **TODO:** Press `gg` to return to the top, then `10j` to land on the Egg Festival entry; that's the Spring festival, and the winner is right there (fact #1)
>
> **TIP:** Don't count lines exactly, overshoot and correct with `k`. It's still faster than scrolling.
>
> **TODO:** Type `/Summer` and hit Enter to jump straight to the Summer section, find the rainy days total (fact #2)
>
> **TIP:** `/` searches the whole file. You don't need to know what line something is on; just one word on it. `n` jumps to the next match if you overshoot.

---

## Quest Log Entry #002

Willy keeps his catch log in one long file, every fish crammed onto a single line.
He needs you to look up three entries before he talks to Gus:

1. What did he sell to Gus, and what grade was it?
2. What was his best catch of the year, and where was it caught?
3. What note did he leave on the Tiger Trout?

These lines are dense; eight fields per line separated by `|`. Without `f`, you're pressing `w` a dozen times per field. With it, you hop directly.

Open the file: `nvim willy-catch-log.txt`

> **TODO:** Find the line mentioning Gus. Press `f|` to jump to the first separator, then `;` to hop to the next
>
> **TIP:** `f|` then `;;;` hops across every separator on the line.
>
> **TODO:** Press `$` to jump to the end of the line and read the `notes` field directly
>
> **TIP:** `0` and `$` snap to the ends instantly; no counting, no scrolling sideways
>
> **TODO:** Type `/Tiger` and hit Enter to jump straight to the Tiger Trout line, or put your cursor on any word and press `*` to search for it instantly
>
> **TIP:** `*` is `/` with zero typing. Cursor on a word, press `*`, vim searches for it. `n` cycles every match in the file.
>
> **TODO:** Use `F|` to jump backward to the previous separator, and `0` to snap back to the start of the line

---

## Checkpoint

- [ ] Used `gg` and `G` to jump to top/bottom of the file
- [ ] Used a numeric multiplier like `10j` or `5w`
- [ ] Used `f<x>` to jump to a specific character on a line
- [ ] Used `F<x>` to jump backward to a character
- [ ] Used `;` to repeat character jump
- [ ] Used `0` and `$` to snap to line start/end
- [ ] Used `/word` to jump to a search match, `n` to cycle results
- [ ] Used `*` to search for the word under the cursor
- [ ] Did not touch the arrow keys or mouse

> Open the next level: `cd ../03-combos` → [03-combos on GitLab](../03-combos)
