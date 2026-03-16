# Level 2 - Navigation Speedrun

> You're in Normal mode. Your hands are on the keyboard.
> The question is: how do you get from where you are to where you need to be?
> Not with arrow keys. Not with the mouse. Faster than that.

---

## The Moves

| Motion | What it does                                              |
| ------ | --------------------------------------------------------- |
| `w`    | Jump forward one word                                     |
| `b`    | Jump backward one word                                    |
| `e`    | Jump to end of current word                               |
| `f<x>` | Jump to next occurrence of character `x` on this line     |
| `F<x>` | Jump to previous occurrence of character `x` on this line |
| `0`    | Jump to start of line                                     |
| `$`    | Jump to end of line                                       |
| `gg`   | Jump to top of file                                       |
| `G`    | Jump to bottom of file                                    |

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
This is the min-max. A single input that scales.

---

## The Patch Notes

This is a long document. Navigate it using only the motions above.
No arrow keys. No mouse. No scrolling.

<!-- TODO: Press `gg`: you should jump instantly to the top of the file -->
<!-- TODO: Press `G`: you should jump instantly to the bottom -->
<!-- TODO: Use `10j` to jump down 10 lines at once, then `10k` to come back -->
<!-- TODO: Find the line with "critical_hit_multiplier" and use `f_` to jump between the underscores -->
<!-- TODO: On the long config line, use `0` to snap to the start, `$` to snap to the end -->
<!-- TODO: Use `5w` to skip across a line 5 words at a time instead of tapping `w` repeatedly -->

```
===============================================================
  PATCH NOTES — DUNGEONS OF ETERNITY v3.1.0
  Released: March 2026
  Developer: Vault Interactive
===============================================================

SECTION 1: BALANCE CHANGES
---------------------------

  Warrior
    - base_attack:               45  →  58
    - armor_penetration:         12  →  18
    - stamina_regen_per_second:  4   →  6
    - rage_cost_per_ability:     20  →  15

  Mage
    - spell_power:               110 →  95
    - mana_pool:                 800 →  750
    - cast_time_multiplier:      1.0 →  1.2
    - mana_regen_per_second:     10  →  8

  Rogue
    - base_attack:               38  →  44
    - critical_hit_multiplier:   1.5 →  1.8
    - critical_hit_chance:       15% →  22%
    - stealth_duration_seconds:  6   →  8

  Healer
    - healing_output_per_cast:   120 →  90
    - cooldown_reduction:        0%  →  10%
    - mana_cost_per_heal:        40  →  35
    - resurrection_cast_time:    4s  →  3s


SECTION 2: BUG FIXES
----------------------

  - [CRIT] Fixed a crash when the inventory contains more than 99 unique item types
  - [CRIT] Fixed incorrect damage calculation when dual-wielding enchanted weapons
  - [HIGH] Fixed players being able to clip through the Northern Gate of Millhaven
  - [HIGH] Fixed the Frost Blade ability dealing 0 damage when cast on moving targets
  - [MED]  Fixed missing floor texture in the Dungeon Boss arena (level 7 and 14)
  - [MED]  Fixed map marker for Quest #048 not displaying on the minimap
  - [LOW]  Fixed the Healer's resurrection animation playing at double speed
  - [LOW]  Fixed a tooltip typo: "critcal" → "critical" on the Rogue skill tree


SECTION 3: KNOWN ISSUES
------------------------

  - Players may experience frame drops when more than 50 entities are loaded simultaneously
  - The Mage ultimate ability has a visual glitch when played on low graphics settings
  - Loot chest sound effect does not play on the first chest opened per session
  - Guild chat history is not persisted across sessions (investigating)
  - The quest tracker UI overlaps the minimap at resolutions below 1280x720


SECTION 4: UPCOMING IN v3.2.0
-------------------------------

  - New dungeon: The Sunken Citadel (8 floors, 3 bosses)
  - Guild housing system
  - Cosmetic item trading between players
  - Controller support improvements
  - Performance pass on all outdoor zones

===============================================================
  END OF PATCH NOTES
  Questions? Join us on Discord: discord.gg/dungsofeternity
===============================================================
```

---

## Checkpoint

- [ ] Used `gg` and `G` to jump to top/bottom instantly
- [ ] Used a numeric multiplier like `10j` or `5w`
- [ ] Used `f<x>` to jump to a specific character on a line
- [ ] Used `0` and `$` to snap to line start/end
- [ ] Did not touch the arrow keys or mouse

> Open the next level: `:q` then `nvim 03-combos.md`
