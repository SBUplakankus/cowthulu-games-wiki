---
icon: lucide/list-tree
---

# Class Structure

## Overview

This is an overview on the current class structure for our game.
**Current Phase:** Pre-Production

Sections will be refined as development progress but for now this page contains the initial design for the first prototype.

## Core

Core classes that are a main part of the Unreal Gameplay Framework we override.

| Name              | Extends        | Function       | Blueprints           |
| ----------------- | -------------- | -------------- | -------------------- |
| `TD_MenuGameMode` | `GameModeBase` | Menu Game Mode | `BP_TD_MenuGameMode` |

## Subsystems

Custom subsystem classes created for the game. Get the Subsystems in blueprints then call their functions

| Name             | Extends                 | Function                                                          | Blueprints      |
| ---------------- | ----------------------- | ----------------------------------------------------------------- | --------------- |
| `TD_UISubsystem` | `GameInstanceSubsystem` | Hosts the Root Layout and Pushes Widgets to their relevant stacks | Use Getter Node |

## Player

Seperate to the character class, these handle the higher level player elements such as control and state.

| Name                  | Extends            | Function                                                    | Blueprints               |
| --------------------- | ------------------ | ----------------------------------------------------------- | ------------------------ |
| `TD_PlayerController` | `PlayerController` | Hosts Input Actions                                         | `BP_TD_PlayerController` |
| `TD_MenuController`   | `PlayerController` | Hosts Input for the Menus                                   | `BP_TD_MenuController`   |
| `TD_PlayerState`      | `PlayerState`      | Hots the players Ability System Component and Attribute Set | `BP_TD_PLayerState`      |


## Characters

For now the only character is the player, but if we add enemies eventually they too will extend from the base class.
All GAS Components need to be stored in the base so we are not duplicating code.

| Name                 | Extends            | Function                                                             | Blueprints              |
| -------------------- | ------------------ | -------------------------------------------------------------------- | ----------------------- |
| `TD_BaseCharacter`   | `Character`        | Base Character class with the Core GAS Components attached           | None - Use Subclasses   |
| `TD_PlayerCharacter` | `TD_BaseCharacter` | Handles player specific elements like `OnPossessed` and the `Camera` | `BP_TD_PlayerCharacter` |

## Gameplay Tags

Gameplay tags that are not used in C++ can be declared in Editor, but any that are need to be referenced in `TDTags.h` and `TDTags.cpp` under the relevant namespace.

This allows us to reference tags safely through a call like `TDTags::TDAbilities:Fireball` instead of trying to pass through a raw string.

### Ability Tags

| Tag      | Usage                              |
| -------- | ---------------------------------- |
| Fireball | Calls the players fireball ability |

### Obstacle Tags

| Tag    | Usage                               |
| ------ | ----------------------------------- |
| OnFire | Triggers the obstacle to be on fire |

## Gameplay Ability System

Components attached to the gameplay ability system

### Abilities

| Name                 | Extends              | Function                                                   | Blueprints            |
| -------------------- | -------------------- | ---------------------------------------------------------- | --------------------- |
| `TD_GameplayAbility` | `GameplayAbility`    | Ability base class with debug toggles and activation calls | None - use subclasses |
| `TD_Fireball`        | `TD_GameplayAbility` | The players primary fireball ability                       | `BP_TD_Fireball`      |

### Attributes

| Name              | Extends        | Function                                                      | Blueprints                  |
| ----------------- | -------------- | ------------------------------------------------------------- | --------------------------- |
| `TD_AttributeSet` | `AttributeSet` | Holds base attributes for characters such as health, mana etc | None - Attach to Characters |

## Common UI 

Classes related to the games frontend through Common UI

| Name                    | Extends                    | Function                                                                     | Blueprints          |
| ----------------------- | -------------------------- | ---------------------------------------------------------------------------- | ------------------- |
| `TD_RootLayout`         | `CommonUserWidget`         | Holds the core widget stacks for the GUI. Modal, Menu, HUD etc.              | `WBP_TD_RootLayout` |
| `TD_ActivateableWidget` | `CommonActivateableWidget` | Base widget for GUI Elements that get pushed to and popped from layer stacks | Use as base class   |
| `TD_ButtonBase`         | `CommonButtonBase`         | Base button class with text                                                  | Use as base class   |

## Utilities

Helpers for the project codebase and blueprints.

| Name                   | Extends                    | Function                                    | Blueprints              |
| ---------------------- | -------------------------- | ------------------------------------------- | ----------------------- |
| `TD_BlueprintLibrary`  | `BlueprintFunctionLibrary` | Holds helper nodes for gameplay blueprints  | Reference the functions |
| `TD_UIFunctionLibrary` | `BlueprintFunctionLibrary` | Holds helper nodes for Common UI Blueprints | Reference the functions |

## Settings

Custom Game Specific Settings pages you can find in Project Settings

| Name            | Extends             | Function                                      | Blueprints |
| --------------- | ------------------- | --------------------------------------------- | ---------- |
| `TD_UISettings` | `DeveloperSettings` | Stores the base layout class and a widget map | None       |