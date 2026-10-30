# Potential Gesture Controls

> Seán Burke
> 27th October 2026

## The Goal

Find a wide variety of controllers that could bring Irish Sign Language to life through a Desktop Game.
This can come in the form of motion controls, gesture recognition, haptic controls, gyroscoping etc.

I will:
- Research Potential Controls
- Get Purchase Cost in Ireland
- Research Unreal Engine 5 Integration

## Potential Controllers

- Ultraleap Leap Motion Controller 2: USB Infared Hand Tracker
- Webcame with Google Mediapipe: Track Hand Movements
- Motion Capture Gloves
- Wii Remote Plus + Nunchuk: Funny Gimmick but could be good
- Modern Gyro Gamepads: Dualsense and Nintendo Switch
- VR Controllers: Experimental but could capture hand motion

## Findings Summary

While I found a wide variety of options, the majority were more gimmicky than feasible, but most importantly did not have direct Unreal Engine 5 integration and software.

All the controller variations would requiring some custom layers made - almost definitely requiring AI assistance and a considerable time sink. This made them more gimmicky - would be funny to show off one day if we have time options over solid examples we could build a prototype off of.

Some of the specialised webcam and glove options were also way too expensive for what would be a mediocre integration anyways, this rule them out pretty early on.

The WebCam is cheapest and quickest integration but it is just manually integrating a software plugin into a game engine - which could be a cool technical challenge but not worth the effort for what I believe would be an underwhelming experience.

This is where the Leap Motion Controller 2 stands out in it's pricing, software and technology. It appears to have peaked in popularity 2-3 years ago when it released, and since faded into relative obscurity, but for our game I think it's a perfect match at a great price.

The company just got bought out and is being merged but that shouldn't effect buying their product.

## Best Option - Leap Motion Controller 2

The Leap Motion Controller 2 is the standout from all the options.
Everyone seems to attach it to VR Headsets but can be used without.
Offers the best out of the box integration.

It does seem to not be available in many places however, and is being sold for over double it's initial launch price.

Cost: [285 Euro](https://eu.robotshop.com/products/ultraleap-leap-motion-controller-2)

Notes:
- Comes with specific gemini software.
- Sold for $129 at launch 3 years ago.
- Small and compact - better than a webcame - offers VR level hand tracking
- Comes with a game for Unity & Unreal - VR Oriented However
- Used by VTubers

Videos:
- [UE5 Car Demo](https://www.youtube.com/watch?v=6pT0TJqJhIM)
- [Ultraleap 2 Intro](https://www.youtube.com/watch?v=WMiNFHdENXM)
- [Basic Tutorial](https://www.youtube.com/watch?v=RGto_SuaBS0)
- [VTuber Guide](https://www.youtube.com/watch?v=KjXcXbGfuDY)

### Important Notice

Turns out it was discontinued 2 years ago, moved to end of life and not available ANYWHERE.
This has one major problem, if we were able to get our hands on one we could make it work, however we would be developing and showcasing a game running on dead tech.
If someone actually loved the game and wanted to set it up somewhere, they wouldn't be able to because they won't have the controller.

## Second Best Option - Google Media Pipe with a Webcam

If we really wanted gesture recognition to the next best option would be a webcam with media pipe. However the gap in viability is quite large.
I would not reccommend it as it hasn't had a well built Unreal Engine plugin since Unreal Engine 4.
Using Media Pipe would involve creating a UE5 Integration layer ourselves, as well as the Python Machine Learning application ourselves.
I don't think this would be a good move for now, would like to spend time developing a game as opposed to developing a plugin for something out of our depth.

## Conclusion

The main takeaway with this motion capture tech I have seen is that it peaked 5-6 years ago and seems to have died off with the progression made by VR and XR Headsets.
Everything I come across has either been abandoned or fully discontinued, for this reason I think we will be best suited going down the route of gamepads with motion controls.
Maybe we can revisit it in the future if there are any developments but for now its a no-go.
