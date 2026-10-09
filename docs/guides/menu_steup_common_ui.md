# Commmon UI Setup Guide

> Seán Burke
> 4th October 2026

## Overview

Since Unreal Engine 5 has it's own framework, there are a couple of steps you need to get used to doing with a new project.
These revolve around the game mode and it's parameters, namely the Player Controller class.
This document will go over the initial steps in order.

### UI Scene Setup

1. Make a Menu Player Controller
2. Create a Game Mode and Assign the new Player Controller
3. Add a Cine Camera Actor to the scene
4. Create your Primary Layout Widget Blueprint
5. Create your Base Button Class
6. Create Common Text Styles
7. Create Common Button Styles 

## Menu Camera

Add a Cine Camera Actor to the scene and position it how you want
The camera needs a Tag named `Default` so it can be found efficiently

## Menu Player Controller

Create a new C++ Class inheriting from Player Controller.
Override the base On Possess function so you can fetch the Camera from the scene.
This will fetch the Cine Cam Actor you place in the scene for your main menu perspective.

```cpp
void AMenuPlayerController::OnPossess(APawn* APawn)
{
	Super::OnPossess(APawn);
	
	TArray<AActor*> FoundCameras;
	UGameplayStatics::GetAllActorsOfClassWithTag(this, ACameraActor::StaticClass(), FName("Default"), FoundCameras);
	
	if (!FoundCameras.IsEmpty())
	{
		SetViewTarget(FoundCameras[0]);
	}
}
```

## Menu Game Mode

Assign the newly created player controller in the slot
Ensure the pawn slot is set to default pawn for now

## Common Text Styles