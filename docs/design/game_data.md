---
icon: lucide/database
---

# Game Data

## Overview

This page is an overview on the data stored in our game from the ISL database to user data we track.

## Irish Sign Language Database

This database is for all of the Irish Sign Language elements of our game from what gets shown in pop ups, through the unlock system and through the in game guide. 

### ISL Data Entry

| Variable              | Function                                 |
| --------------------- | ---------------------------------------- |
| `int: Id`             | General entry identifier                 |
| `string: Name`        | English name                             |
| `string: VideoPath`   | Path to the visual demonstration         |
| `enum: EntryType`     | Dance, Pop-Up, Info                      |
| `enum: Category`      | Dances, Animals, Environment, General    |
| `bool: IsUnlockable`  | Whether it starts the game hideen or not |
| `string: UnlockEvent` | Name of the event sent out to unlock it  |

**EntryTypeEnum:** `Dance`, `Pop-Up`, `Info`

**CategoryEnum:** `Dances`, `Animals`, `Environment`, `General`

### ISL Data Tables


| Id  | Name     | VideoPath           | EntryType | Category | IsUnlockable | UnlockEvent      |
| --- | -------- | ------------------- | --------- | -------- | ------------ | ---------------- |
| 0   | Fireball | `movies/signs/fire` | `Dance `  | `Dances` | `True`       | `UnlockFireball` |

