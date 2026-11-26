---
icon: lucide/flame
---

# Gameplay Ability System

## Overview

The abilities in our game run off of Unreal Engine 5's Gameplay Ability system, this document is for all the related assets in the project.

[GAS Documentation](https://dev.epicgames.com/documentation/unreal-engine/gameplay-ability-system-for-unreal-engine)

The Core GAS Assets used in our project include:

| Name       | Function                                                                                        |
| ---------- | ----------------------------------------------------------------------------------------------- |
| Attributes | Attached to components ie. `Health`, `Mana`                                                     |
| Abilities  | The actual abilities triggered by input actions ie. `GA_TD_Fireball`                            |
| Effects    | Effects applied to entities after being hit by an ability ie. `OnFire`, `HitReact`              |

## Attributes

| Name      | Function                                         |
| --------- | ------------------------------------------------ |
| Health    | Defines the current health of an entity          |
| MaxHealth | Defines the maximum possible health of an entity |
| Mana      | Defines the current mana of an entity            |
| MaxMana   | Defines the maximum possible mana of an entity   |

## Abilities

| Name             | Function                                  |
| ---------------- | ----------------------------------------- |
| `GA_TD_Fireball` | Called by the player to launch a fireball |

## Effects

| Name           | Function                                    |
| -------------- | ------------------------------------------- |
| `GE_TD_OnFire` | Applied when an entity has been set on fire |


