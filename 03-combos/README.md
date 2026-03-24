# Level 3: Verb + Noun = Combo

> Navigation gets you there fast. Combos let you act on what's there.
>
> Three verbs: `c` (change), `d` (delete), `y` (copy).
> A handful of nouns: `iw` (word), `i"` (inside quotes), `i(` (inside parens).
> Any verb works with any noun. That's not a shortcut list; it's a system.
> Learn the verbs once, learn the nouns once, and they combine forever.
>
> This is where Vim stops feeling different and starts feeling faster.

---

## The Combos

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

## Quest Log Entry #001

Pierre just installed a new point-of-sale system. The demo install defaulted to JojaMart settings;
his shop name, email, currency, everything is wrong. He's furious.
Every bad value is already wrapped in quotes. `ci"` gets you inside them from anywhere on the line.

Open the file: `nvim pierre-config.txt`

> **TODO:** Put your cursor anywhere on a line with a wrong value
>
> **TODO:** Press `ci"`, everything inside the quotes is wiped and you're in insert mode
>
> **TIP:** Cursor doesn't have to be inside the quotes, anywhere on the line works
>
> **TODO:** Type the correct value, press `Esc`, move to the next wrong line
>
> **TIP:** Each fix is the same motion: `ci"`, type, `Esc`. Build the muscle memory

Correct values (in order):

- `Pierre's General Store`
- `pierre@pelicantownshop.com`
- `gold`
- `Thanks for shopping local!`

---

## Quest Log Entry #002

Sebastian is freelancing to build the Pelican Town community website.
He roughed in all the API calls with generic first-draft args and needs the real ones before launch.
`ci(` wipes everything inside the parentheses; all of them, at once, from anywhere on the line.

Open the file: `nvim sebastian-site.js`

> **TODO:** Put your cursor anywhere on the line — on the function name, before the parens, anywhere
>
> **TODO:** Press `ci(`, every argument inside is wiped and you're in insert mode inside empty parens
>
> **TIP:** Doesn't matter how many args are inside or where they are. `ci(` clears the whole thing.
>
> **TIP:** Same pattern as `ci"`; just a different delimiter. `c i <delimiter>` works for `"`, `(`, `[`, `{`
>
> **TODO:** Type the correct arguments, press `Esc`, move to the next call

Correct arguments (in order):

- `(authorId, "Spring Planting Tips", content)`
- `(commentId, moderatorId)`
- `(eventId, "Egg Festival", date)`

---

## Quest Log Entry #003

Gunther finally has enough donations to update the museum catalog.
The dig site confirmed the real IDs, but whoever entered them got the numbers wrong.
Retyping risks more errors; yank the correct ID, select the wrong one, paste to replace.

Open the file: `nvim gunther-catalog.txt`

> **TODO:** Put your cursor on `ANCIENT_DOLL_004` in the comment and press `yiw` to yank it
>
> **TIP:** `yiw` yanks the whole word no matter where on it your cursor is.
>
> **TODO:** Navigate to the wrong ID on Entry #1, press `viw` to select it, then `p` to paste over it
>
> **TIP:** In visual mode, `p` replaces the selection with what you yanked — one keystroke swap
>
> **TODO:** Repeat for the remaining entries; yank the correct ID from the comment, `viw` + `p` on the wrong one

---

## Quest Log Entry #004

The JojaMart server is finally being decommissioned, good riddance.
There are two blocks of legacy entries that need to go, and `debug_mode` was left on in production.
Use `3dd` to delete each block, `cc` to fix the wrong value.

Open the file: `nvim joja-server.yaml`

> **TODO:** Put your cursor on the first legacy entry line (below the `DEPRECATED` comment) and press `3dd`; all 3 lines gone
>
> **TIP:** `3dd` deletes and you stay in Normal mode. No insert, nothing to type.
>
> **TODO:** Do the same for the second `DEPRECATED` block
>
> **TODO:** Find `debug_mode`, press `cc` to wipe the line, type `debug_mode: false`, press `Esc`
>
> **TIP:** `cc` wipes the line but keeps the indentation; ready for the replacement

---

## Quest Log Entry #005

The Traveling Merchant's reserved items weren't picked up; they all need to go back to `available`.
Some are already `available`. You only need to touch the `reserved` ones.
Make the first change manually. Every one after that is just navigation + `.`.

Without `.`, that's `cw`, type `available`, `Esc`; five separate times. With `.`, it's that once, then a single keystroke per fix after. Same result, a fraction of the work.

Open the file: `nvim traveling-cart.txt`

> **TODO:** Navigate to the first `reserved` and press `cw`, type `available`, press `Esc`
>
> **TIP:** `cw` changes from cursor to end of word. Cursor needs to be at the start of the word.
>
> **TODO:** Move to the next `reserved` and press `.`; it replays everything: the delete, the typed text, the escape
>
> **TIP:** `.` repeats the FULL last change. Motion, text, everything. One keystroke.
>
> **TODO:** Repeat for every remaining `reserved`; one keystroke each

---

## Final Checkpoint

- [ ] Used `ci"` without having to position cursor inside the quotes
- [ ] Used `ci(`, same move, different delimiter
- [ ] Used `yiw` + `viw` + `p` to yank a word and swap it in without retyping
- [ ] Used `3dd` to delete multiple lines in one command
- [ ] Used `cc` to wipe and rewrite a line
- [ ] Used `.` to repeat a change instead of retyping it
- [ ] Know `r<x>` replaces a single character without entering insert mode

---

> **Workshop complete.**
>
> This is the Stardew logic: every motion you learn is a permanent upgrade. `ci"` saves keystrokes and prevents you from moving your hand from the home row.
> `.` saves 50. Multiplied across every file you'll ever edit, for the rest of your career, it compounds.
> There's always a faster way. That's the whole game.
>
> **Next steps:**
>
> - `vimtutor`: free, built-in, 30 minutes, run it right now
> - Vim Adventures at vim-adventures.com: learn through gameplay
> - The VSCode Vim extension: same muscle memory, your current environment
