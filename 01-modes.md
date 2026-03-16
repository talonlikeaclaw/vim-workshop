# Level 1 - Select Your Mode

> Vim has modes. This is the thing that confuses everyone at first.
> Most editors only have one mode: you open the file, you type.
> Vim separates _navigating_ from _typing_. That separation is the whole point.
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

In a normal editor, every keypress either types a character or triggers a shortcut.
You reach for the mouse constantly. You highlight with click-and-drag.

In Vim, your entire keyboard is a control panel in Normal mode.
`d` deletes. `y` copies. `w` jumps a word. No Ctrl, no Alt, no mouse.
The speed comes from keeping your hands on the home row, always.

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

`o` is the one you'll reach for constantly while coding: you're on a line and want to add something below it. `o` to "Open" line below. No navigating to the end of the line first.

---

## Quest Log Entry #001

The guild scribe saved the wrong status on this quest.
Fix it using insert mode.

<!-- TODO: Use `w` to hop to the word "ABANDONED" (or click there — just this once) -->
<!-- TODO: Press `i` to enter insert mode -->
<!-- TODO: Delete "ABANDONED" and type "COMPLETED" -->
<!-- TODO: Press `Esc` to return to Normal mode -->
<!-- TODO: Type `:w` and hit Enter to save -->

```
QUEST: The Missing Shipment
DATE:  2026-03-01
STATUS: COMPLETE

The cargo was recovered from the bandit camp north of Millhaven.
All 12 crates accounted for. Reward has been paid out.
This quest is complete and should be marked as such.
```

---

## Quest Log Entry #002

The reward is missing. Add it.

<!-- TODO: Navigate to the empty line after "REWARD:" -->
<!-- TODO: Press `i`, type the reward: 1200 gold + Enchanted Cloak -->
<!-- TODO: Press `Esc`, then `:w` to save -->

```
QUEST: Slay the Wyvern of Black Crag
DATE:  2026-03-04
STATUS: COMPLETED
REWARD:

Notes: Completed by a party of three. No casualties. Wyvern confirmed dead.
The village of Black Crag is safe. They want a monument built apparently.
```

---

## Checkpoint

- [ ] Can enter insert mode with `i`
- [ ] Can return to Normal mode with `Esc`
- [ ] Can save with `:w`
- [ ] Know that `Esc` is always the way back to safety

> Open the next level: `:q` then `nvim 02-navigation.md`
