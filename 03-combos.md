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
| `p`   | **p**aste  | —                  | Paste what you yanked                               |
| `cc`  | **c**hange | whole **line**     | Wipe entire line, enter insert                      |
| `3dd` | **d**elete | **3** lines        | Delete 3 lines at once                              |

> `i` = **inside**: excludes surrounding characters
> `a` = **around**: includes surrounding characters

---

## The Config File

The server config has outdated values. Every wrong value is inside quotes.
Without `ci"` you'd double-click to select, delete, retype. Every. Single. One.
With `ci"` you put your cursor anywhere on the line and fire the combo.

<!-- TODO: Put your cursor anywhere on a line with a wrong value -->
<!-- TODO: Type `ci"`: the content inside the quotes disappears and you're in insert mode -->
<!-- TODO: Type the correct value, press `Esc`, move to the next line -->
<!-- TODO: Notice you never had to precisely position your cursor inside the quotes -->

```
[server_config]

database_host     = "localhost"
database_name     = "prod_BROKEN_NAME_FIX_THIS"
database_user     = "root_WRONG_CHANGE_TO_admin"
database_password = "hunter2_THIS_IS_NOT_THE_PASSWORD_CHANGE_TO_s3cur3p4ss!"
api_base_url      = "http://old-api.internal.corp.net/v1/DEPRECATED"
cdn_url           = "https://cdn-old.assets.io/static/NEEDS_UPDATING"
log_level         = "verbose_CHANGE_TO_error"
environment       = "staging_WRONG_THIS_IS_PRODUCTION"
```

Correct values (in order):

- `prod_db`
- `admin`
- `s3cur3p4ss!`
- `http://api.internal.corp.net/v2`
- `https://cdn.assets.io/static`
- `error`
- `production`

---

## The Ability Refactor

A junior dev wrote these ability calls with placeholder arguments.
Each one needs the arguments wiped and replaced.

`da(` deletes the parentheses AND everything inside them.
Then you type the new call from scratch.
Try doing that by click-dragging from `(` to `)` on each line. It's painful.
Now try `da(`. One combo. Gone.

<!-- TODO: Put your cursor anywhere on a line -->
<!-- TODO: Use `f(` to jump your cursor to the opening parenthesis -->
<!-- TODO: Type `da(`: the entire (...) block is deleted -->
<!-- TODO: Type the new arguments, e.g. (playerId, "fire", 95) -->

```
// Ability calls - replace all placeholder arguments

castAbility(PLACEHOLDER_REMOVE_AND_RETYPE_playerId_fire_95)
applyStatusEffect(PLACEHOLDER_REMOVE_AND_RETYPE_targetId_poisoned_true)
spawnEnemy(PLACEHOLDER_REMOVE_AND_RETYPE_zoneId_dragon_elite)
calculateDamage(PLACEHOLDER_REMOVE_AND_RETYPE_baseDmg_multiplier_isCrit)
triggerCutscene(PLACEHOLDER_REMOVE_AND_RETYPE_sceneId_skipAllowed_true)
```

Correct calls (in order):

- `(playerId, "fire", 95)`
- `(targetId, "poisoned", true)`
- `(zoneId, "dragon", "elite")`
- `(baseDmg, multiplier, isCrit)`
- `(sceneId, skipAllowed, true)`

---

## The Loot Drop Table

The item IDs appear once in the comments and need to be duplicated into
the actual table entries below. Without `yiw` you'd retype each one.
With `yiw` you yank it once and paste it as many times as you need.

<!-- TODO: Put your cursor on an item ID in the comment (e.g. "IRON_SWORD_047") -->
<!-- TODO: Type `yiw` to copy it: nothing visible happens but it's in your register -->
<!-- TODO: Move your cursor to the corresponding empty slot in the table -->
<!-- TODO: Type `p` to paste -->
<!-- TODO: Repeat for each item -->

```
// Item IDs defined by the asset team — copy these into the table below:
// IRON_SWORD_047  CHAINMAIL_VEST_112  AMULET_OF_POWER_009  PHANTOM_STEED_331

| Slot      | Item ID              | Drop Rate | Rarity   |
|-----------|----------------------|-----------|----------|
| Weapon    |                      | 8%        | Uncommon |
| Armor     |                      | 5%        | Rare     |
| Accessory |                      | 2%        | Epic     |
| Mount     |                      | 0.5%      | Legendary|
```

---

## The Dead Code

Three blocks of dead config need to go. Each is clearly marked.
`cc` wipes one line and drops you into insert mode.
`3dd` deletes 3 lines at once without entering insert mode — nothing to retype.

Think about what it takes to manually delete 3 lines without these:
Home key, Shift+End, Delete, repeat three times. Or triple-click three times.

<!-- TODO: Put your cursor on the first line of a DEPRECATED block -->
<!-- TODO: Type `3dd` to delete all 3 lines at once -->
<!-- TODO: For the single-line entries, use `cc` and retype the corrected version -->

```yaml
# Active config
max_players: 200
tick_rate: 64
region: eu-west-1

# DEPRECATED — delete these 3 lines
legacy_host: "old-server-07.internal"
legacy_port: 8012
legacy_protocol: "tcp-v1"

# Active config continues
enable_anticheat: true
enable_replay_system: true

# DEPRECATED — delete these 3 lines
old_matchmaking_url: "http://mm-legacy.corp.net"
old_matchmaking_key: "key_AAAABBBBCCCC"
old_matchmaking_version: "v0.9"

# Active config continues
log_retention_days: 30
max_log_size_mb: 500

# Wrong value — use `cc` to fix this line
debug_mode: true_WRONG_SHOULD_BE_false
```

---

## Final Checkpoint

- [ ] Used `ci"` without having to precisely position cursor inside the quotes
- [ ] Used `da(` to nuke an argument list in one move
- [ ] Used `yiw` + `p` to copy and paste a word without retyping it
- [ ] Used `3dd` to delete multiple lines in a single command
- [ ] Used `cc` to wipe and rewrite a line

---

> **Workshop complete.**
> You've been here 15 minutes and you already know more Vim than most developers.
> The skill ceiling from here is basically infinite.
> `vimtutor` is free, built-in, and takes 30 minutes.
> Vim Adventures at vim-adventures.com if you want to keep it fun.
> The VSCode Vim plugin if you're not ready to go full terminal.
