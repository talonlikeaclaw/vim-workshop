# Level 3: Verb + Noun = Combo

> Navigation gets you there fast. Combos let you act on what's there.
>
> Three verbs: `c` (change), `d` (delete), `y` (copy).
> A handful of nouns: `iw` (inside word), `i"` (inside quotes), `i(` (inside parens).
>
> Any verb works with any noun; that's not a shortcut list, it's a language.
> Learn the verbs once, learn the nouns once, and they combine forever.
>
> This is where Vim stops feeling different and starts feeling faster.

---

**Ensure you are here:** `03-combos/pierre-config.txt` (check bottom status line).

---

## Quest #5: Fix Pierre's Config

Scenario: Pierre's POS system defaulted to JojaMart settings — shop name, email, currency, and greeting are all wrong. Every bad value is wrapped in quotes.

> 1. Cursor anywhere on a wrong value line
> 2. `ci"` -> wipes inside quotes, enter insert
> 3. Type correct value, `Esc`, next line

**Tip**: Cursor doesn't have to be inside the quotes -> anywhere on the line works.
**Tip**: Same motion every time: `ci"`, type, `Esc`. Build the muscle memory.

Correct values (in order):

- `Pierre's General Store`
- `pierre@pelicantownshop.com`
- `gold`
- `Thanks for shopping local!`

---

## Quest #6: Update Sebastian's Site

Switch files: `:e sebastian-site.js`

Scenario: Sebastian's API calls have placeholder args; the real ones are needed before launch.

> 1. Cursor anywhere on the line
> 2. `ci(` -> all args wiped, enter insert inside empty parens
> 3. Type correct args, `Esc`, next call

**Tip**: Doesn't matter how many args or where -> `ci(` clears them all.
**Tip**: `c i <delimiter>` works for `"`, `(`, `[`, `{` -> same pattern every time.

Correct arguments (in order):

- `(authorId, "Spring Planting Tips", content)`
- `(commentId, moderatorId)`
- `(eventId, "Egg Festival", date)`

---

## Quest #7: Fix Gunther's Catalog

Switch files: `:e gunther-catalog.txt`

Scenario: The dig site confirmed the real artifact IDs; whoever entered them got the numbers wrong. Yank the correct ID from the comment, swap it in with `viw` + `p`.

> 1. Cursor on `ANCIENT_DOLL_004` in the comment, `yiw` to yank
> 2. Navigate to wrong ID on Entry #1, `viw` to select, `p` to paste over
> 3. Repeat for remaining entries

**Tip**: `yiw` yanks the whole word wherever the cursor is.
**Tip**: In visual mode, `p` replaces the selection -> one keystroke swap.

---

## Quest #8: Clean the Joja Server

Switch files: `:e joja-server.yaml`

Scenario: The JojaMart server is being decommissioned. Two legacy entry blocks need to go, and `debug_mode` was left on in production.

> 1. Cursor on the first legacy entry (below `DEPRECATED`), `3dd` -> all 3 lines gone
> 2. Repeat for the second `DEPRECATED` block
> 3. Find `debug_mode`, `cc`, type `debug_mode: false`, `Esc`

**Tip**: `3dd` deletes and you stay in Normal mode. No insert needed.
**Tip**: `cc` wipes the line but keeps indentation -> ready for the replacement.

---

## Quest #9: Fix the Traveling Cart

Switch files: `:e traveling-cart.txt`

Scenario: The Traveling Merchant's items weren't picked up! Change the `reserved` ones back to `available`.

> 1. Navigate to first `reserved`, `cw`, type `available`, `Esc`
> 2. Move to next `reserved`, press `.` -> replays the whole change
> 3. Repeat for every remaining `reserved`

**Tip**: `cw` changes cursor to end of word — start at the beginning of the word.
**Pro tip**: Without `.`: five `cw` + type + `Esc`. With `.`: once, then one key each.

---

## Quick Reference

| Combo  | Verb        | Noun               | What it does                                                 |
| ------ | ----------- | ------------------ | ------------------------------------------------------------ |
| `ci"`  | **c**hange  | **i**nside quotes  | Wipe everything inside `"..."`, enter insert                 |
| `ci(`  | **c**hange  | **i**nside parens  | Wipe everything inside `(...)`, enter insert                 |
| `da(`  | **d**elete  | **a**round parens  | Delete `(...)` including the parentheses themselves          |
| `yiw`  | **y**ank    | **i**nner **w**ord | Copy the word your cursor is on                              |
| `viw`  | **v**isual  | **i**nner **w**ord | Select the word your cursor is on                            |
| `p`    | **p**aste   | -                  | Paste yanked text; in visual mode, replaces selection        |
| `cc`   | **c**hange  | whole **line**     | Wipe entire line, enter insert                               |
| `3dd`  | **d**elete  | **3** lines        | Delete 3 lines at once                                       |
| `.`    | **repeat**  | last change        | Replay your last edit exactly as-is                          |
| `r<x>` | **r**eplace | single char        | Replace the character under cursor with `x` — no insert mode |

> `i` = **inside**: excludes surrounding characters
> `a` = **around**: includes surrounding characters

---

## Checkpoint

- [ ] `ci"` from anywhere on the line
- [ ] `ci(`, same move, different delimiter
- [ ] `yiw` + `viw` + `p` to swap words without retyping
- [ ] `3dd` deletes N lines in one command
- [ ] `cc` wipes and rewrites a line
- [ ] `.` repeats the last change
- [ ] `r<x>` replaces a char without insert mode

---

> **Workshop complete.**
>
> This is the Stardew logic: every motion you learn is a permanent upgrade.
> `ci"` saves keystrokes and keeps your hands on the home row.
> `.` saves 50. Multiplied across every file you'll ever edit, it compounds.
> There's always a faster way. That's the whole game.
>
> **Next steps:**
>
> - `vimtutor`: free, built-in, 30 minutes
> - Vim Adventures at vim-adventures.com: learn through gameplay
> - The VSCode Vim extension: same muscle memory, your current environment
