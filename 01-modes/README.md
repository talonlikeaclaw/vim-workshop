# Level 1: Select Your Mode

> Vim has modes. This is the thing that confuses everyone at first.
> Most editors only have one mode: you open the file, you type.
> Vim separates _navigating_ from _typing_. That separation is the _whole point_.
> Normal mode is home base. You spend most of your time here.

---

## The Modes

| Mode        | Enter with | What it's for                                       |
| ----------- | ---------- | --------------------------------------------------- |
| **Normal**  | `Esc`      | Moving, deleting, copying; everything except typing |
| **Insert**  | `i`        | Actually typing new text                            |
| **Visual**  | `v`        | Selecting text                                      |
| **Command** | `:`        | Save, quit, find & replace                          |

---

## Why Does This Matter?

In a normal editor you reach for the mouse constantly. Every edit is a context switch.
In Vim, your entire keyboard is a control panel in Normal mode:
`d` deletes, `y` copies, `w` jumps a word. No Ctrl, no Alt, no mouse. **Hands on the home row, always.**

---

## Getting Into Insert Mode

`i` is the basic entry point, but there are six ways in. Each places your cursor differently, saving you extra keystrokes before you start typing.

| Key | Inserts at...                   |
| --- | ------------------------------- |
| `i` | Before the cursor               |
| `a` | After the cursor                |
| `I` | Start of the line               |
| `A` | End of the line                 |
| `o` | New line below the current line |
| `O` | New line above the current line |

`o` is the one you'll use most while coding: you're on a line and want to add something below it. No need to navigate to the end of the line first.

---

## Moving Around

Once you're in a file, use `hjkl` to move in Normal mode: `h` left, `j` down, `k` up, `l` right.

`j` and `k` are right on the home row. Even YouTube uses them: `k` pauses, `j`/`l` skip backward/forward. You already know these without realising it.

---

## Quest Log Entry #001

Pierre's shop ledger has a mistake. Last season's seed order got marked `ABANDONED` but it was fulfilled. Fix it before he notices.

Open the file: `nvim pierre-ledger.txt`

> **TODO:** Use `j` to move down to the STATUS line
>
> **TIP:** `j` moves down, `k` moves up. Arrow keys work too, but try to stay on `hjkl`
>
> **TODO:** Press `A` to jump to the end of the line and enter insert mode
>
> **TIP:** `A` saves you from navigating to the end manually, it jumps and switches mode in one keystroke
>
> **TODO:** Backspace over "ABANDONED" and type "COMPLETED"
>
> **TODO:** Press `Esc` to return to Normal mode
>
> **TIP:** If you ever feel lost, `Esc` always gets you back to Normal mode
>
> **TODO:** Type `:w` and hit Enter to save

---

## Quest Log Entry #002

Robin finished your barn upgrade but forgot to log the materials cost.
Mayor Lewis needs it for the town budget. Add it before the next council meeting.

Open the file: `nvim robin-carpentry.txt`

> **TODO:** Use `j` / `k` to navigate to the "MATERIALS:" line
>
> **TODO:** Press `o` to open a new line below it; you drop straight into insert mode
>
> **TIP:** `o` beats navigating to end of line then pressing Enter, it does both in one key
>
> **TODO:** Type the materials: "- 550g, 150 Wood, 100 Stone"
>
> **TODO:** Press `Esc`, then `:w` to save

---

## Checkpoint

- [ ] Can enter insert mode with `i`, `a`, and `o`
- [ ] Know the difference: `i` (before cursor), `a` (after), `o` (new line below)
- [ ] Can return to Normal mode with `Esc`
- [ ] Can save with `:w`
- [ ] Know that `Esc` is always the way back to safety

> Open the next level: `cd ../02-navigation` → [02-navigation on GitLab](../02-navigation)
