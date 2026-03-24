# Level 2: Navigation Speedrun

> Normal mode = **control panel**. No arrows, no mouse.
> Just **precise jumps** to anywhere.

---

**Ensure you are here:** `02-navigation/town-calendar.txt` (check bottom status line).

---

## Quest #3: Find 3 Facts for Mayor Lewis

Scenario: Find the Spring winner, Summer rainy days count, and council note.

> 1. `G` -> bottom (council note)
> 2. `gg` -> top, `10j` -> Egg Festival (Spring winner)
> 3. `/Summer` + Enter -> rainy days

**Pro tip**: `Ctrl+d` / `Ctrl+u` jumps half a page down/up — faster than holding `j`/`k` on long files.

---

## Quest #4: Scan Willy's Catch Log

Switch files: `:e willy-catch-log.txt`

Scenario: Dense log, 8 fields per entry. Find the Tiger Trout's catch date. weight, grade, and notes.

> 1. `/Tiger` or `*` (on word) -> Tiger Trout
> 2. `f|` -> first `|`, `;;` -> hop fields (repeat last f)
> 3. `$` -> line end (notes field)
> 4. `0` -> line start (date field)

**Pro tip**: `f|` + `;` chains across pipes. `*` searches with zero typing.

---

## Quick Reference

| Type       | Keys                               | Examples       |
| ---------- | ---------------------------------- | -------------- |
| **Words**  | `w` (fwd), `b` (back), `e` (end)   | `5w`, `3b`     |
| **Chars**  | `f<char>`, `F<char>`, `;` (repeat) | `f(`, `;;`     |
| **Lines**  | `0` (start), `$` (end), `#j/k`     | `10j`, `G`     |
| **File**   | `gg` (top), `G` (bottom)           | -              |
| **Page**   | `Ctrl+d` (down), `Ctrl+u` (up)     | -              |
| **Search** | `/word`, `*` (cursor), `n/N`       | `*`, `/Summer` |

**Multiplier:** Prefix any: `5w`, `3b`, `4f|`

---

## Checkpoint

- [ ] `gg`/`G` file ends, `Ctrl+d`/`Ctrl+u` half-page jumps
- [ ] Multipliers (`10j`)
- [ ] `f`/`;` field hopping
- [ ] `/` & `*` search
- [ ] `$` & `0` line hopping
- [ ] No arrows/mouse!

**Next:** `:cd ../03-combos/` -> `:e pierre-config.txt` -> [Level 3](../03-combos/)
