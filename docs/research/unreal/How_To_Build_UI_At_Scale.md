# How to Build UI at Scale: Lessons from Marvel’s 'Midnight Suns' 
> Unreal Fest Orlando 2025  
> Seán Burke  
> 28th September 2026

## Overview

Presentation about a way you can make UI at Scale for a game released in 2022.

## Video

<div class="video">
  <iframe src="https://www.youtube-nocookie.com/embed/Pm2jswrHSck" title="How to Build UI at Scale" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen loading="lazy"></iframe>
</div>

## Important Notes

1. This is for a game released in 2022 that was likely in development from 2019 onwards
2. It uses a very game engine style component system
3. Game Engines have started to move towards a .NET MVVM UI Architecture the last few years, this preceeds that
4. Too abstract to make sense for a year long project
5. It doesn't use current UE5 Common UI

## Scale

| Problem | Type |
| --- | --- |
| Screen Complexity | Depth |
| Amount of Screens | Breadth |

## Terminology

| Term | What is it? |
| --- | --- |
| Screen | Base of the UI system |
| Widget | Visual UI Element |
| Control | Interactable Widget |
| Screen Component | A class that provides functionality that can be added to a screen |

## User Interface Component System

### The Problem - What do I need to do?

Break UI Implementation into Components?

- Get Data
- Display Data
- Respond to User Actions

### Getting Data - Data Screen Component

- Retrieve Data
- Comes back as a TArray<UObject>* 
- Optional Filters and Transforms
    - I need to sort the data in a certain way

### Displaying Data - View Component

- Create & Cache Widgets
- Add to a Container
- Give Data to Widgets
- Provide Widget Callbacks
- You create instances of widgets instead of just referencing a sub class
    - This gives you the variables every widget has
    - More flexible than choosing a class

### Responding - Action Screen Components

- Gather Data required for action
- Determine if action can happen
- Executing the action

## Communication

- Get Components through Functions
- Delegates
- Component Selectors

### Get Components through Functions

All Screens, Widgets and Screen Components have

- ScreenComponentType* GetScreenComponent<ScreenComponentType>()
- TArray<ScreenComponentType*> GetAllScreenComponents<ScreenComponentType>()
- ScreenComponentType* GetScreenComponentByName<ScreenComponentType>(FName)

These are all available in Blueprints aswell

### Delegates

So components can communicate between each other

- OnDataRetrieved
- OnClick
- OnFocus
- OnActionAttempt

### Component Selectors

Gives you a list of all the components on the screen you're editing so you can select what you want to listen to

## Character Select Example

What do we want to do?

1. Get a list of all characters unlocked
2. Display them
3. When selected display them on a screen

What happens?

1. Data Screen Component fetches the unlocked heroes
2. It fires of it's delegate when completed
3. The view screen component is listening to this
4. It will create the buttons and send the data so the icons can appear
5. When someone clicks on one of the icons, the view screen broadcasts the action saying this is whats clicked heres the data
6. The action screen component takes this and opens the character selected screen in response

The System is Data Driven as its designed to avoid boilerplate. No C++ or Blueprints needed.

The Character Inventory screen then has all of these, but it also has an entry screen component.
This allows it to broadcast out that it's data has been changed so it is entry as data can be entered.

Why is this good?

1. It simplifies the interactions between screens
2. You don't need to know anything about the screens themselves
3. You only need to know about the component you want to interact with

## Composing Widgets

- Composable Widget
    - Widget Layer
    - Widget Layer
    - Widget Layer

Allows layers to be independant and put in different configurations.

### Layer Examples

- Icons
    - Boost
    - Upgrade
    - Currency
    - Amount of Something 

- Chest Widget
    - New Item Icon 
    - Item Icon
    - Cash Amount
    - Rarity Border

- Inventory Item
    - Boosted or Not
    - Whether its Damaged
    - Item Icon

- Store Item
    - Item Icon
    - Cost

- Consumable
    - Item Icon
    - How many you have

## Not all screens

Settings screens are well trotten ground you don't need to over complicate it, just make them like usual.

## How did UICS work for them

- There is a bit of initial set up due to it being Data Driven
- Once it was set up it was more efficient and took less effort 
    - Easier to share functionality across screens
    - Data permutations
- Learning Curve
    - About 3 Months
- Consistency and workflow for UI Creation
- Less Defects

