# Vim Motions Workshop

> _You already min-max in the games you play. Now do it for your text navigation._
>
> _This isn't the "memorize 200 shortcuts" pitch. It's 10 moves that combine. 15 minutes from now you'll get why people won't shut up about vim._

Welcome to the follow-along repo for the Vim Motions workshop.
Each folder is a level. Open the README on GitLab to read the instructions,
then open the practice files in nvim alongside it.

`cd 01-modes` - **[→ Get Started](01-modes/)**

## Levels

| Folder                           | Topic               | Key Moves                                        |
| -------------------------------- | ------------------- | ------------------------------------------------ |
| [01-modes/](01-modes/)           | Modes & basics      | `i` `a` `o`, `Esc`, `:w`, `u`                    |
| [02-navigation/](02-navigation/) | Navigation & search | `w` `b`, `f` `;`, `gg` `G`, `/` `*`, multipliers |
| [03-combos/](03-combos/)         | Verb + noun combos  | `ci"` `ci(`, `yiw` `p`, `3dd`, `.`               |

## How to Use This Repo

1. Open the level's `README.md` here on GitLab, that's your reference
2. In your terminal, `cd` into the level folder and open the practice file in nvim
3. Follow the quest steps from the README

```bash
cd 01-modes
nvim pierre-ledger.txt
```

## Emergency Exit

If you're stuck and can't get out:

```
Esc
:q!
```

`Esc` gets you back to Normal mode. `:q!` force quits without saving.
Everyone needs this at least once. Usually in the first 5 minutes.

---

_Workshop content made with help from [Claude Code](https://claude.ai/code)._
