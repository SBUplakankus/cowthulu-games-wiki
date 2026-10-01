---
icon: lucide/layout-dashboard
---

# 20 Things You Should Be Using in Unreal Motion Graphics 
> Unreal Fest Gold Coast 2024  
> Watched 28th September 2026

## Video

<div class="video">
  <iframe src="https://www.youtube-nocookie.com/embed/0NHIIMDkIMA" title="20 Things You Should Be Using in UMG" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen loading="lazy"></iframe>
</div>

## UMG / CommonUI

### UI Material Lab
- Epic sample project with UI material functions and examples.
- [Documentation](https://dev.epicgames.com/community/learning/tutorials/Wz8V/unreal-engine-intuitive-material-building-with-the-ui-material-lab-part-1)

### Play Animation Forward / Reverse
- Use for hover/unhover animations.
- Plays from the current animation state instead of restarting.

### Stack Box
- Stacks children vertically or horizontally.
- Can replace separate Vertical Box / Horizontal Box layouts in suitable cases.

### Common Visual Attachment
- Attaches a visual element without changing the layout size of the attached widget.
- Useful for badges, markers, prompts, and similar overlays.
- [UE 5.8 API](https://dev.epicgames.com/documentation/en-us/unreal-engine/API/Plugins/CommonUI/UCommonVisualAttachment)

### Common Text Block
- Supports text overflow handling and marquee-style scrolling.
- Use with hover/unhover events for interactive text.
- [UE 5.8 API](https://dev.epicgames.com/documentation/unreal-engine/API/Plugins/CommonUI/UCommonTextBlock)

### Text Overflow Policy - Ellipsis
- Displays an ellipsis when text does not fit.

### Wrap Box
- Automatically wraps child widgets onto additional lines.
- [UE 5.8 API](https://dev.epicgames.com/documentation/en-us/unreal-engine/API/Runtime/UMG/UWrapBox)

### Spacer
- Invisible layout widget used to take up space.
- Useful for animating the position of other content.
- [UE 5.8 API](https://dev.epicgames.com/documentation/en-us/unreal-engine/API/Runtime/UMG/USpacer)

### Apply Line Height to Bottom Line
- Controls whether line-height space is applied below the final line.
- Useful for vertically centering multiline text.

### Monospacing
- Forces characters to use a consistent width.
- Useful for text and animated numbers where changing character widths would cause movement.
- Relevant font settings: `bForceMonospaced`, `MonospacedWidth`.
- [UE 5.8 API](https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/SlateCore/FSlateFontInfo)

### Common Numeric Text Block
- Animates/interpolates numeric values.
- [UE 5.8 API](https://dev.epicgames.com/documentation/unreal-engine/API/Plugins/CommonUI/UCommonNumericTextBlock)

## Performance

### Global Invalidation
- Reduces unnecessary UMG layout and paint work.
- [UE 5.8 guidance](https://dev.epicgames.com/documentation/unreal-engine/optimization-guidelines-for-umg-in-unreal-engine)

### Slate Prepass
- Some widgets and layouts require additional measurement passes.
- Watch for **Scale Box**, **Size Box**, **Rich Text**, and **auto-wrapped text**.
- Talk example: approximately **577 µs → 24 µs** after removing an expensive layout setup.
- [UE 5.8 guidance](https://dev.epicgames.com/documentation/unreal-engine/optimization-guidelines-for-umg-in-unreal-engine)

### Snap to Pixel
- Disable for smoother animated or scrolling text when sub-pixel movement is desirable.

### Editor Utility Widgets
- Create custom editor tools and dockable editor panels using UMG.
- [Documentation](https://dev.epicgames.com/documentation/en-us/unreal-engine/scripting-the-unreal-editor-using-blueprints)

## Slate Postbuffers

### Slate Postbuffers
- Used for UI blur and other post-process effects.
- Effects can be layered.
- UE 5.8: **Experimental**.
- Supports up to **5 Slate postbuffers**.
- [Documentation](https://dev.epicgames.com/documentation/unreal-engine/using-slate-postbuffers-in-unreal-engine)

### Post Buffer Update
- Controls where and when a Slate postbuffer is populated.
- [UE 5.8 API](https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/UMG/UPostBufferUpdate)

### Slate Post Processors
- Process Slate postbuffers.
- Includes `USlatePostBufferBlur`.
- [UE 5.8 API](https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/SlateBaseRenderer/USlatePostBufferBlur)

### Sampling Slate Postbuffers
- UI materials can sample `GetSlatePost0` through `GetSlatePost4`.

### Examples
- Epic's Content Examples project includes `UI_SlatePostBuffer`.
- Examples include blur, masking, tinting, vignettes, and distortion.
- Effects can be layered.
