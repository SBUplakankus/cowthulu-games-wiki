# Common UI Overview

> Seán Burke  
> 3rd October 2026

## What is Common UI?

It is a plugin for User Inferaces in UE5 Developed originally for Fortnite but has since been adopted for all of Epic's games and larger samples.

## What problems does it solve?

- Managing multiple layers of UI where only the top should receive input.
- Handling Gamepad navigation and focus.
- Supporting different input devices and controller layouts.
- Displaying the correct button prompts for the current active platform
- Managing Activation and Deactivation of Widgets
- Cleanly Handling Navigation between menus

## Key Components

### Activatable Widgets

Provides an explict active / inactive state for a UI Screen or component.

Useful for
- Main Menus
- Settings
- Inventory
- Pause Menus
- Confirmation Modals & Dialogs
- Pop-Up Windows
- Submenus

The Activatable Widget remains in the UI Hierarchy while being inactive. 
This allows Common UI to determine which UI Layer should currently receive input.
The widgets don't need to be constructed and destroyed every time.

### Activatable Widget Stacks

Activatable Widget Stakcs provide a stack based way of managing screens with Push and Pop functionality.

These stacks work in different layers such as
- Menu
- Modal
- HUD
- Notificaations

### Input Routing

Input Routing is what makes Common UI's navigation work. 
It routs through the hierarchy of activatable widgets based on the layer order.

### Common Input

Common UI uses a system for describing Abstract UI Actions
- Accept
- Back
- Confirm
- Cancel
- Navigate
- Custom Special Actions

All of these can be mapped to different physical inputs based on the platform and controller.
For example an abstract back action can be represented by different physical buttons.
Controller Data Assets work with this to also provide the correct button icons for each platform and controller.

### Common Widgets & Styles

Common UI provides its own version of widgets like buttons text etc.
These can all be styled with central style assets. 
This allows for centralised UI customisation without needing to touch every single element of a widget.

## What advantages does it have?

- Better support for complex menu hierarchies thanks to layers of widget stacks.
- Improved Controller support.
- Platform specific button prompts.
- Shared styling.
- Clean menu lifecycle.
- Scales better for large frontends.
- Seperation of UI Actions from Physical inputs with abstract actions.

## What disadvantages does it have?

- Additional complexity
- More setup
- Migrating a project to Common UI takes time
- Not every widget should be an activateable widget ie. Static HUD Elements
- Not suitable for World Space UI

## Documentation

- [Index](https://dev.epicgames.com/documentation/unreal-engine/common-ui-plugin-for-advanced-user-interfaces-in-unreal-engine?lang=en-US)
- [Overview](https://dev.epicgames.com/documentation/unreal-engine/overview-of-advanced-multiplatform-user-interfaces-with-common-ui-for-unreal-engine)
- [Quickstart Guide](https://dev.epicgames.com/documentation/unreal-engine/common-ui-quickstart-guide-for-unreal-engine)
- [API](https://dev.epicgames.com/documentation/unreal-engine/API/Plugins/CommonUI)
- [Design Guidelines](https://dev.epicgames.com/documentation/unreal-engine/design-guidelines-for-using-commonui-in-unreal-engine?lang=en-US)
- [Input Technical Guide](https://dev.epicgames.com/documentation/unreal-engine/commonui-input-technical-guide-for-unreal-engine)

## Videos

- [Introduction - 2:41:30](https://www.youtube.com/watch?v=TTB5y-03SnE&t=4213s&pp=ygUJY29tbW9uIHVp)
