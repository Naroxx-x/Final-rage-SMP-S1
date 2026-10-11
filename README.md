# RageSMP

A Rage-based PvP progression plugin for Paper 1.21.11.

## Rage
- New players start at Rage 3 (`starting-rage`), and Rage can never go below 1 (`min-rage`).
- Kill: +1 Rage
- Death: -1 Rage (nothing is lost at Rage 1)
- Maximum: 5
- If the killer is already at max Rage, they gain nothing: a **Rage Shard**
  drops on the ground instead. Any player can pick it up and **right-click it**
  to convert it into Rage. A victim already at Rage 1 drops no shard.
- `/rage withdraw <amount>` converts your own Rage into physical shards
  (never below Rage 1).
- Every Rage gain or loss is shown in **bold purple in chat** (in addition to
  the action bar).

## Bonuses per level
- **Rage 1**: normal damage, and Blood Combo — after 3 consecutive sword hits on
  the same target, every hit after that is critical until you miss a swing.
- **Rage 2**: +10% damage, permanent Speed I.
- **Rage 3**: +15% damage, +2 hearts.
- **Rage 4**: +20% damage, +4 hearts, and Armor Break — after 5 consecutive
  hits on the same target, the next hit ignores part of their armor.
- **Rage 5**: +25% damage, +6 hearts, sword hits break the target's raised
  shield for 2 seconds, and the **Ultimate**.

All levels keep every ability of the levels below them.

## Ultimate (Rage 5)
1. Land **10 sword hits in a row without missing a swing**. **READY** appears in
   bold purple in chat.
2. **Sneak + right-click with a sword** to activate it.
3. For **10 seconds**, every sword hit is a critical, and purple particles
   surround you so your opponent can see it is active.

Dropping below Rage 5 (for example by dying) forfeits a READY Ultimate.
The hit count, duration and more are configurable in `config.yml`.

Commands:
- `/rage`
- `/rage <player>`
- `/rage withdraw <amount>`
- `/setrage <player> <1-5>` (admin)

## Build
Compiling requires downloading the `paper-api` dependency from
`repo.papermc.io`, so an internet connection is required.

```
./gradlew build
```

The compiled plugin will be at `build/libs/RageSMP-1.0.0.jar`.
