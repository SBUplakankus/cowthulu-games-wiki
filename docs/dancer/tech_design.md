# The Dancer - Technical Design

> Seán Burke
> 
> 30th October 2026

## About

This document will discuss the early technical design and concepts for the dancer ahead of our Concept Presentation.

Note: *This is just the summary of the initial research and findings ahead of the initial Unreal Engine 5 Implementation.*

## Project Details

**Title:** The Dancer
**Engine:** Unreal Engine 5.8
**Version Control:** Diversion
**Genre:** Action RPG
**Perspective:** Top Down
**Art Style:** 3D Stylised Fantasy
**Unreal Plugins:** FlatNodes, Diversion, GAS, Common UI

## Unreal Plugins

What specialised plugins will we have enabled in our Unreal Engine 5 project.

| Plugin | What does it do? |
| --- | --- |
| **Flat Nodes** | Simplified Blueprint node styling that makes graphs easier to read and understand |
| **Diversion** | Direct engine integration for Diversion Version Control |
| **Gameplay Ability System** | For advanced gameplay down the line provides Attributes, Tags, Gameplay Effects and Gameplay Abilities |
| **Common UI** | Advanced Frontend Plugin driven by abstract user actions and UI Navigation through UI Layers and Activatable Widget Stacks |

## The User Interface

The User Interface will play a crucial role in our game's educational aspect.
To be an effective experience, especially for a younger audience, we need to make sure players can get everything they need in-game without having to spend ages in menus, reading material before-hand, or constantly tabbing out to read material externally.
Everything MUST be provided through the flow of the game.

Developing our UI with Common UI gives us three major advantages:
1. Built in Controller Navigation
2. Abstract UI Actions ie. Confirm, Back etc. will in theory allow us to navigate the UI how we need.
3. Clear seperation of layers with Stack Navigation will allow us to cleanly navigate deep menus such as a full menu wiki on ISL.

## The Gesture Detection & Motion Controls

This was the most dissapointing aspect so far but motion detection through specialised devices and software will likely not be possible for now.
We did have luck however with motion controls and came up with a promising concept for handling fingure detection.
The gyroscoped controllers such as the Playstation DualShock and Switch Joycons would be perfect candidates for detection user hand motions, we can then come up with an intuative user input for each of the fingers. 

After doing some research we believed the Leap Motion Controller 2 would be the perfect device. It had software, a UE5 Plugin and great functionality for what we wanted, but the product was discontinued over 2 years ago and moved to end of life. This was after Leapmotion were merged with another company who went on to can their XR division.

This puts us in a tough situation where:
1. Buying a controller is incredibly difficult and expensive.
2. We would be making a product build around dead tech, that if someone was interested in, they couldn't actually use because they also can't buy the device.

After doing some digging I discovered that consumer standalone hand detection never took off as a product, instead XR and VR devices began integrating hand detection as a core feature and developers moved away from consumer products to industry manufacturing.

Another option for WebCam detection would be integrating Google Media Pipe into UE5, but that would be a large amount of work.
There have not been any serious attempts at this since UE4 over 5 years ago so it would a large undertaking. 
It isn't simple hand detection, it is a machine learning library you have to train yourself. 

Due to all this, our focus in pre-production will be aimed at a motion-control gamepad system with custom built finger position toggling.

## Production Plan

Some Must Have, Should Have, Could Have and Won't Have features.

| Priority | Feature |
| --- | --- |
| **Must Have** | Educational ISL Elements |
| **Should Have** | Generic Gesture Controls |
| **Could Have** | 3D ISL Representation |
| **Won’t Have** | VR / XR Gameplay |

## Anticipated Challenges

Some of the issues we will need to tackle as the project progresses.

### Tactile Controls

Ensuring that the user can correctly sign using the game controller and the game can pick it up effectively will be the biggest technical challenge.

### Educational Effectiveness

Will players come out of the experience feeling like they learned anything meaningful about Irish Sign Language after playing?
Will our systems be able to represent ISL well enough and teach enough information in-game?

### ISL Representation In Game

Being able to effectively represent Irish Sign Language in game through UI, 3D and Animations will require custom motion-capture.


