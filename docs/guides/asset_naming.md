# Naming Conventions

## Overview

This guide is for naming assets within the Unreal Engine 5 project through both the C++ Classes and Editor Classes.

We are going to use standard UE5 naming conventions but with a project specific prefix following that.

For us the prefix is `TD`.

It is mandatory to follow these guides. UE5 comes with hundreds of built in classes so when trying to access our project specific assets in editor, adding TD to the search query will narrow it down.

The core rule is: `[AssetTypePrefix]_TD_[AssetName]_[OptionalVariant]`

**Some examples:**

- `BP_TD_PlayerCharacter`
- `WBP_TD_MainMenu`
- `BP_TD_Obstacle_Vines`

**General rules:**

- Use PascalCase for descriptive names: PlayerCharacter, MainMenu.
- Separate words with capitals; do not use spaces or hyphens.
- Use clear, descriptive names. Avoid names such as NewAssetBob, Test2 or Final_Final_FinalForReal.
- Add a suffix only when it helps identify a variant, function or texture map.
- Keep third-party assets in separate folders and do not rename them.

As you use the editor more this will make more sense to you. 

C++ Classes don't need a prefix so they are all `TD_ClassName`.

If you don't follow these guidelines on pull requests they are going to be denied and you'll have to fix them!

---

## Common Asset Prefixes

If any are missing let me know and I will add them, but this should cover what we need.

| Prefix  | Asset type          | Example                     |
| ------- | ------------------- | --------------------------- |
| `BP_`   | Blueprint Class     | `BP_TD_PlayerCharacter`     |
| `BPI_`  | Blueprint Interface | `BPI_TD_Interactable`       |
| `BPC_`  | Blueprint Component | `BPC_TD_Health`             |
| `E_`    | Enum                | `E_TD_CharacterState`       |
| `ST_`   | Struct              | `ST_TD_CharacterStats`      |
| `DT_`   | Data Table          | `DT_TD_CharacterStats`      |
| `DA_`   | Data Asset          | `DA_TD_CharacterSettings`   |
| `SK_`   | Skeletal Mesh       | `SK_TD_BaseCharacter`       |
| `SKEL_` | Skeleton            | `SKEL_TD_BaseCharacter`     |
| `SM_`   | Static Mesh         | `SM_TD_Rock`                |
| `ABP_`  | Animation Blueprint | `ABP_TD_PlayerCharacter`    |
| `A_`    | Animation Sequence  | `A_TD_Player_Idle`          |
| `AM_`   | Animation Montage   | `AM_TD_Player_Attack`       |
| `BS_`   | Blend Space         | `BS_TD_Player_Locomotion`   |
| `M_`    | Material            | `M_TD_Character_Master`     |
| `MI_`   | Material Instance   | `MI_TD_Character_Body`      |
| `MF_`   | Material Function   | `MF_TD_WorldAlignedTexture` |
| `T_`    | Texture             | `T_TD_Character_Body_D`     |
| `WBP_`  | Widget Blueprint    | `WBP_TD_MainMenu`           |
| `NS_`   | Niagara System      | `NS_TD_DustImpact`          |
| `S_`    | Sound Wave          | `S_TD_Footstep_Concrete`    |
| `SC_`   | Sound Cue           | `SC_TD_Footsteps`           |
| `MS_`   | Meta Sound          | `MS_TD_Wind`                |
| `LVL_`  | Level / Map         | `LV_TD_MainLevel`           |

## Texture Suffixes

Use these to identify texture maps.
Example: `T_TD_Character_Body_N`

| Suffix | Meaning                                  |
| ------ | ---------------------------------------- |
| `_D`   | Base Colour / Diffuse                    |
| `_N`   | Normal                                   |
| `_R`   | Roughness                                |
| `_M`   | Metallic                                 |
| `_AO`  | Ambient Occlusion                        |
| `_ORM` | Packed Occlusion, Roughness and Metallic |
| `_E`   | Emissive                                 |

> Last Updated: Seán Burke - 21st November 2026