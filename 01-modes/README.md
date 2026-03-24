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

## The Payoff

In a normal editor: reach for the mouse, click to position, back to keyboard, type, repeat. Every single edit.
In Vim, your entire keyboard is a control panel in Normal mode:
`d` deletes, `y` copies, `w` jumps a word: no Ctrl, no Alt, no mouse. **Hands stay on the home row.**

---

## Getting Into Insert Mode

`i` is the basic way in, but there are others. The quests below use `i`, `A`, and `o`: the rest are there when you want them.

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

`j` and `k` are right on the home row. Even YouTube uses them: `k` pauses, `j`/`l` skip 10s backward/forward.

---

## Undo & Redo

| Key      | What it does         |
| -------- | -------------------- |
| `u`      | Undo last change     |
| `Ctrl+r` | Redo (undo the undo) |

`u` is your safety net. Made a mistake? Press `u`. You can undo as many times as you need; this is what lets you experiment freely.

---

## Quest Log Entry #001

Pierre's shop ledger has a mistake. Last season's seed order got marked `ABANDONED` but it was fulfilled. Fix it before he notices.

Open the file: `nvim pierre-ledger.txt`

> **TODO:** Use `j` to move down to the `STATUS` line
>
> **TIP:** `j` moves down, `k` moves up. Arrow keys work too, but try to stay on `hjkl`
>
> **TODO:** Press `A` to jump to the end of the line and enter insert mode
>
> **TIP:** `A` is two actions in one: jump to end of line + enter insert. In any other editor you'd click there first.
>
> **TODO:** Backspace over `ABANDONED` and type `COMPLETED`
>
> **TODO:** Press `Esc` to return to Normal mode
>
> **TIP:** If you ever feel lost, `Esc` always gets you back to Normal mode
>
> **TODO:** Type `:w` and hit Enter to save
>
> **TIP:** You just backspaced 9 characters to delete a word. In Level 3, you'll do that in 2 keystrokes. That's where this is going.

---

## Quest Log Entry #002

Robin finished your barn upgrade but forgot to log the materials cost.
Mayor Lewis needs it for the town budget. Add it before the next council meeting.

Open the file: `nvim robin-carpentry.txt`

> **TODO:** Use `j` / `k` to navigate to the `MATERIALS:` line
>
> **TODO:** Press `o` to open a new line below it; you drop straight into insert mode
>
> **TIP:** `o` is three actions collapsed into one: go to end of line, press Enter, enter insert mode. One key.
>
> **TODO:** Type the materials: `- 550g, 150 Wood, 100 Stone`
>
> **TODO:** Press `Esc`, then `:w` to save

---

## Checkpoint

- [ ] Can enter insert mode with `i`, `a`, and `o`
- [ ] Know the difference: `i` (before cursor), `a` (after), `o` (new line below)
- [ ] Can return to Normal mode with `Esc`
- [ ] Can save with `:w`
- [ ] Know that `Esc` is always the way back to safety
- [ ] Can undo with `u` and redo with `Ctrl+r`

> Open the next level: `cd ../02-navigation` → [02-navigation on GitLab](../02-navigation)
