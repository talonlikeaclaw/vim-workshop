# Level 1: Select Your Mode

> Vim's secret: **separate navigation from typing**.
>
> `Esc` = **home base** (Normal mode). Everything starts here.
>
> Undo: `u`, Redo: `Ctrl + r`
>
> Insert: (`i`/`I`) / Append: (`a`/`A`) / Open: (`o`/`O`) = enter typing (Insert mode).

---

**Open the first file**: `nvim pierre-ledger.txt`

---

## Quest #1: Fix Pierre's Ledger

Scenario: Last season's seed order says `ABANDONED` - change it to `COMPLETED`.

> 1. Use `j` to move down to `STATUS` line (`j` = down, `k` = up, `h` = left, `l` = right)
> 2. Press `A` (end of line + Insert mode)
> 3. Backspace `ABANDONED`, type `COMPLETED`
> 4. `Esc` → Normal mode
> 5. `:w` + Enter to save (the command prompt is at the bottom)

**Stuck?** `Esc` always returns to Normal Mode. `:q!` force quits.

---

## Quest #2: Log Robin's Materials

Switch files: type `:e robin-carpentry.txt` (you can press Tab to auto-complete)

Scenario: Add materials cost under `MATERIALS:` line.

> 1. `j`/`k` to `MATERIALS` line
> 2. `o` (new line below + Insert mode)
> 3. Type: `- 550g, 150 Wood, 100 Stone`
> 4. `Esc`, then `:w`

**Pro tip**: `o` = end of line + Enter + Insert. **One key**, _three actions_.

---

## Quick Reference

| When             | Keys                                                            |
| ---------------- | --------------------------------------------------------------- |
| **Enter typing** | `i` (cursor), `a` (after), `A` (line end), `o` (new line below) |
| **Exit typing**  | `Esc`                                                           |
| **Move**         | `h` = left, `j` = down, `k` = up, `l` = right                   |
| **Undo**         | `u`                                                             |
| **Redo**         | `Ctrl + r`                                                      |
| **Save**         | `:w`                                                            |
| **Switch file**  | `:e filename`                                                   |

---

## Checkpoint

- [ ] Fixed Pierre's ledger
- [ ] Added Robin's materials
- [ ] `Esc` feels natural

**Next:** `:e ../02-navigation/town-calendar.txt` [Level 2](../02-navigation/)
