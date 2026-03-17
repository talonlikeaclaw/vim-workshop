# Level 3 - Verb + Noun = Combo

> Navigation gets you there fast. Combos let you operate with precision.
> A verb + a noun = a single command that does exactly what you mean.
> No highlighting. No clicking. No selecting character by character.
> Your cursor is already there. One combo. Done.

---

## The Combos

| Combo | Verb       | Noun               | What it does                                        |
| ----- | ---------- | ------------------ | --------------------------------------------------- |
| `ci"` | **c**hange | **i**nside quotes  | Wipe everything inside `"..."`, enter insert        |
| `ci(` | **c**hange | **i**nside parens  | Wipe everything inside `(...)`, enter insert        |
| `da(` | **d**elete | **a**round parens  | Delete `(...)` including the parentheses themselves |
| `yiw` | **y**ank   | **i**nner **w**ord | Copy the word your cursor is on                     |
| `p`   | **p**aste  | -                  | Paste what you yanked                               |
| `cc`  | **c**hange | whole **line**     | Wipe entire line, enter insert                      |
| `3dd` | **d**elete | **3** lines        | Delete 3 lines at once                              |
| `.`   | **repeat** | last change        | Replay your last edit exactly as-is                 |

> `i` = **inside**: excludes surrounding characters
> `a` = **around**: includes surrounding characters

---

## Quest Log Entry #001

Pierre just installed a new point-of-sale system. The demo install defaulted to JojaMart settings;
his shop name, email, currency, everything is wrong. He's furious.
Every bad value is already wrapped in quotes. `ci"` gets you inside them from anywhere on the line.

Open the file: `nvim pierre-config.txt`

<!-- TODO: Put your cursor anywhere on a line with a wrong value -->
<!-- TODO: Press `ci"`, everything inside the quotes is wiped and you're in insert mode -->
<!-- TODO: Type the correct value, press `Esc`, move to the next wrong line -->
<!-- TODO: Notice you never need to click inside the quotes, `ci"` finds them automatically -->

Correct values (in order):

- `Pierre's General Store`
- `pierre@pelicantownshop.com`
- `gold`
- `0.07`
- `http://pelican-supply.net/api/v2`
- `Thanks for shopping local!`
- `pelican_town`

---

## Quest Log Entry #002

Sebastian is freelancing to build the Pelican Town community website.
He stubbed out all the API calls with placeholder args and now needs them filled in before the launch.
`ci(` is the same move as `ci"`, just a different delimiter. Cursor anywhere on the line, fire the combo.

Open the file: `nvim sebastian-site.js`

<!-- TODO: Put your cursor anywhere on the line, even on the function name works -->
<!-- TODO: Press `ci(`, everything inside the parentheses is wiped and you're in insert mode -->
<!-- TODO: Type the correct arguments from the list, press `Esc` -->
<!-- TODO: Repeat for each call, notice you never have to aim at the parentheses -->

Correct arguments (in order):

- `(authorId, "Spring Planting Tips", content)`
- `(commentId, moderatorId)`
- `(memberId, displayName, avatarUrl)`
- `(eventId, "Egg Festival", date)`
- `(channelId, message, isPinned)`

---

## Quest Log Entry #003

Gunther finally has enough donations to update the museum catalog.
The artifact IDs were confirmed by the dig site and left in a comment at the top of the file.
They need to go into the donation log below. Retyping them risks transcription errors; use `yiw` to yank and `p` to paste.

Open the file: `nvim gunther-catalog.txt`

<!-- TODO: Put your cursor on an artifact ID in the comment (e.g. ANCIENT_DOLL_004) -->
<!-- TODO: Press `yiw`, the whole ID is yanked (nothing visible happens, but it's in your register) -->
<!-- TODO: Navigate to the corresponding entry line -->
<!-- TODO: Press `$` to jump to the end of the line, cursor lands on the `:` -->
<!-- TODO: Press `p` to paste, the ID appears right after the colon -->
<!-- TODO: Repeat for each artifact -->

---

## Quest Log Entry #004

The JojaMart server is finally being decommissioned, good riddance.
There are two blocks of legacy entries that need to go, and `debug_mode` was left on in production.
Use `3dd` to delete each block, `cc` to fix the wrong value.

Open the file: `nvim joja-server.yaml`

<!-- TODO: Put your cursor on the first legacy entry line (not the comment, the data line below it) -->
<!-- TODO: Press `3dd`, all 3 lines are deleted at once without entering insert mode -->
<!-- TODO: Do the same for the second DEPRECATED block -->
<!-- TODO: Find the `debug_mode` line, it should be `false` in production -->
<!-- TODO: Press `cc`, the line is wiped and you're in insert mode -->
<!-- TODO: Type `debug_mode: false`, press `Esc` -->

---

## Quest Log Entry #005

The Traveling Merchant's reserved items weren't picked up; they all need to go back to `available`.
Some are already `available`. You only touch the `reserved` ones.
Make the first change manually. Every one after that is just navigation + `.`.

Open the file: `nvim traveling-cart.txt`

<!-- TODO: Navigate to the first `reserved` line and position cursor on the word `reserved` -->
<!-- TODO: Press `cw` → type `available` → press `Esc` -->
<!-- TODO: Move to the next `reserved` line, put cursor on `reserved` again -->
<!-- TODO: Press `.`, it replays the entire last change: cw + "available" + Esc -->
<!-- TODO: Repeat for every reserved item, one keystroke per fix instead of retyping each time -->

---

## Final Checkpoint

_Check the boxes with `r` (replace) `x`_

- [ ] Used `ci"` without having to position cursor inside the quotes
- [ ] Used `ci(`, same move, different delimiter
- [ ] Used `yiw` + `p` to copy and paste without retyping
- [ ] Used `3dd` to delete multiple lines in one command
- [ ] Used `cc` to wipe and rewrite a line
- [ ] Used `.` to repeat a change instead of retyping it

---

> **Workshop complete.**
> You've been here 15 minutes and you already know more Vim than most developers.
> The skill ceiling from here is basically infinite.
> `vimtutor` is free, built-in, and takes 30 minutes.
> Vim Adventures at vim-adventures.com if you want to keep it fun.
> The VSCode Vim plugin if you're not ready to go full terminal.
