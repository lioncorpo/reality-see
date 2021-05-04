---
title: What is a hologram?
description: HoloLens lets you view and interact with three-dimensional holograms, objects made of light and sound that appear in the world around you.
author: hferrone
ms.author: v-hferrone
ms.date: 03/21/2018
ms.topic: article
keywords: Windows Mixed Reality, HoloLens, holograms, design, interaction, mixed reality headset, windows mixed reality headset, what is augmented reality
---

# What is a hologram?

<iframe width="940" height="530" src="https://www.youtube.com/embed/MVXH5V8MVQo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


HoloLens lets you create **holograms**, which are objects made of light and sound that appear in the world around you like real objects. Holograms respond to your [gaze](../design/gaze-and-commit.md), [gestures](../design/gaze-and-commit.md#composite-gestures), and [voice commands](../design/voice-input.md). They can even interact with [real-world surfaces](../design/spatial-mapping.md) around you. With holograms, you can create digital objects that are part of your world.

<br>

## Device support

<table>
    <colgroup>
    <col width="25%" />
    <col width="25%" />
    <col width="25%" />
    <col width="25%" />
    </colgroup>
    <tr>
        <td><strong>Feature</strong></td>
        <td><a href="/hololens/hololens1-hardware"><strong>HoloLens (1st gen)</strong></a></td>
        <td><a href="https://docs.microsoft.com/hololens/hololens2-hardware"><strong>HoloLens 2</strong></td>
        <td><a href="../discover/immersive-headset-hardware-details.md"><strong>Immersive headsets</strong></a></td>
    </tr>
     <tr>
        <td>Holograms</td>
        <td>✔️</td>
        <td>✔️</td>
        <td>❌</td>
    </tr>
</table>

<br>

---

## A hologram is made of light and sound

The holograms that HoloLens [renders](../develop/platform-capabilities-and-apis/rendering.md) appear in the holographic frame directly in front of the user's eyes. Holograms add light to your world, which means that you see both the light from the display and the light from your surroundings. HoloLens doesn't remove light from your eyes, so holograms can't be rendered with the color black. Instead, black content appears as transparent.

Holograms can have many different appearances and behaviors. Some are realistic and solid, and others are cartoonish and ethereal. You can use holograms to highlight features in your surroundings or use them as elements in your app's user interface.

![Hands manipulating a hologram](images/hologram-hands-940px.jpg)

Holograms can also make [sounds](../design/spatial-sound.md), which will appear to come from a specific place in your surroundings. On HoloLens, sound comes from two speakers that are located directly above your ears, without covering them. Similar to the displays, the speakers are additive, introducing new sounds without blocking the sounds from your environment.

<br>

---

## A hologram can be placed in the world or tag along with you

When you have a particular location for a hologram, you can [place](../design/coordinate-systems.md) it precisely at that point in the world. As you walk around, the hologram appears stable based on the world around you. If you use a [spatial anchor](../design/coordinate-systems.md#spatial-anchors) to pin the object, the system can even remember where you left it when you come back later.

![Two men using Microsoft Dynamics 365 Layout in a retail space](images/HLS19_retailLayoutHologram_001-940px.jpg)

Some holograms follow the user instead, positioning themselves based on the user no matter where they walk. You may even choose to bring a hologram with you for a while and then place it on the wall once you get to another room.

**Best practices**
* Some scenarios may demand that holograms remain easily discoverable or visible throughout the experience. There are two high-level approaches to this kind of positioning. Let's call them **"display-locked"** and **"body-locked"**.
   * Display-locked content is positionally "locked" to the device display. This type of content is tricky for several reasons, including an unnatural feeling of "clingyness" that makes many users frustrated and wanting to "shake it off." In general, many designers have found it better to avoid display-locking content.
   * The body-locked approach is far more forgivable. Body-locking is when you tether a hologram to the user's body or gaze vector in 3d space. Many experiences have adopted a body-locking behavior where the hologram "follows" the users gaze, which allows the user to rotate their body and move through space without losing the hologram. Incorporating a delay helps the hologram movement feel more natural. For example, some core UI of the Windows Holographic OS uses a variation on body-locking that follows the user's gaze with a gentle, elastic-like delay while the user turns their head.
* Place the hologram at a comfortable viewing distance typically about 1-2 meters away from the head.
* Provide a drift amount for elements that must be continually in the holographic frame, or consider animating your content to one side of the display when the user changes their point of view.

**Place holograms in the optimal zone - between 1.25 m and 5 m**

Two meters is the most optimal, and the experience will degrade the closer you get from 1 meter. At distances nearer than 1 meter, holograms that regularly move in depth are more likely to be problematic than stationary holograms. Consider gracefully clipping or fading out your content when it gets too close so you don't jar the user into an unexpected experience.

![Optimal distance for placing holograms from the user.](images/distanceguiderendering-950px.png)

<br>

---

## A hologram interacts with you and your world

Holograms aren't only about light and sound; they're also an active part of your world. Gaze at a hologram and gesture with your hand, and a hologram can start to follow you. Give a voice command to a hologram, and it can reply.

![Group of government utility workers using Microsoft HoloLens 2 to collaborate on a wind farm development project](images/HLS19_governmentUtilitiesHologram_001-940px.jpg)

Holograms enable personal interactions that aren't possible elsewhere. Because the HoloLens knows where it is in the world, a holographic character can look you directly in the eyes as you walk around the room.

A hologram can also interact with your surroundings. For example, you can place a holographic bouncing ball above a table. Then, with an [air tap](../design/gaze-and-commit.md#composite-gestures), watch the ball bounce, and make sound when it hits the table.

Holograms can also be occluded by real-world objects. For example, a holographic character might walk through a door and behind a wall, out of your sight.

**Tips for integrating holograms and the real world**
* Aligning to gravitational rules makes holograms easier to relate to and more believable. for example: Place a holographic dog on the ground & a vase on the table rather than have them floating in space.
* Many designers have found that they can integrate more believable holograms by creating a "negative shadow" on the surface that the hologram is sitting on. They do this by creating a soft glow on the ground around the hologram and then subtracting the "shadow" from the glow. The soft glow integrates with the light from the real world, which uses the shadow to ground the hologram in the environment.

<br>

---

:::row:::
    :::column:::
        ## A hologram is whatever <br>you can dream up<br>
        As a holographic developer, you have the power to break your creativity out of 2D screens and into the world around you.<br><br>
        What will *you* build?
    :::column-end:::
        :::column:::
        ![space](images/spacer-20x582.png)<br>
       ![Holographic imaginary world in living room](images/designoverview.jpg)<br>
    :::column-end:::
:::row-end:::

<br>

---

## Next Discovery Checkpoint

If you're following the [discovery journey](get-started-with-mr.md) we've laid out, you're in the midst of exploring the basics of Mixed Reality. From here, you can continue to the next foundational topic: 

> [!div class="nextstepaction"]
> [Expand your design process](case-study-expanding-the-design-process-for-mixed-reality.md)