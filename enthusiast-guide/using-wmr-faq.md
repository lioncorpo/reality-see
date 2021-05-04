---
title: Using Windows Mixed Reality FAQ
description: Find resources to common questions when working with Windows Mixed Reality applications and hardware.
author: hferrone
ms.author: v-hferrone
ms.date: 09/15/2020
ms.topic: article
keywords: Windows Mixed Reality, Mixed Reality, Virtual Reality, VR, MR, Feedback, Feedback Hub, bugs
appliesto:
    - Windows 10
---

# Using Windows Mixed Reality FAQ

If you need help with using your Windows Mixed Reality immersive headset, check out these topics for general info and troubleshooting.

Still need help? For advanced troubleshooting, check out this article.

## I see a message that says “Lost tracking” or “We don’t have a boundary for this space.”

Select **Start > Mixed Reality Portal** on your desktop. Select **Menu**, then select **Run setup** to create a new boundary. Windows Mixed Reality supports multiple locations and will identify the space you are in at startup as long as the room hasn’t changed.  

## I can’t hear any sound, or the sound is coming from my computer instead of my headset

If your immersive headset doesn’t include built-in headphones, you’ll need to connect headphones to the audio jack on the headset. (The jack is often located just behind the headset visor or lenses; check with your headset manufacturer if you have trouble finding it.) 

Some audio headsets have physical buttons to control the volume. If audio isn't working, check whether the volume is turned down or muted.

Windows Mixed Reality is designed to play sound through your immersive headset when you’re wearing it and have headphones connected to it. When you take off the headset or flip the visor up, audio will switch to your default Windows playback device. You can change this setting in **Settings > Mixed reality > Audio and speech**.

> [!NOTE]
> * Windows Mixed Reality spatial audio works best with headphones built into or connected directly to your immersive headset. PC speakers or headphones connected to the PC might not work well for spatial audio.
> * Windows Mixed Reality doesn’t support Bluetooth audio headsets.

## Speech commands aren’t working

To use Speech commands, your PC’s speech and language settings must be set to a [supported Windows Mixed Reality region and language](other-questions.md#what-languages-are-supported-in-windows-mixed-reality). To check your Windows region and language, select **Settings > Time & language > Region & language**. To check your Speech language, select **Settings > Time & language > Speech**.

If your headset doesn’t have a built-in mic, attach a pair of headphones with a mic to your headset or PC. Select **Settings > Mixed reality > Audio and speech** to automatically switch your mic input to your headset when your headphones are connected. Make sure that **When I wear my headset, switch to headset mic** is turned on.

Some audio headsets have a physical button to mute and unmute the microphone. If Speech commands aren't working, check whether your mic is muted.

## The boundary is always visible. How can I make it go away?

When you’re close to the boundary, it appears. If your boundary includes any sections that have a narrow or irregular shape, you might end up getting close to it—and causing it to appear—more often than you’d like. To fix this, try creating your boundary again, using a larger and more regular shape. Select **Start > Mixed Reality Portal** on your desktop, then select **Run setup**. 

You can also temporarily turn off the boundary from Mixed Reality Portal: select **Menu**, then use the toggle to turn off the boundary. When the boundary is turned off, you'll need to stay in one spot to avoid obstacles.

## I’m having trouble with my motion controllers

If your motion controllers aren’t working properly, aren't connecting, or if you don’t see an image of the controllers when you’re wearing your headset:

* Make sure your controllers are turned on. To turn them on, press and hold the **Windows** button for 2 seconds.
* Select **Start > Mixed Reality Portal** on your PC and then select **Menu** You should see your motion controllers listed, along with a status message:
    * Ready – The controllers are all set.
    * Lost tracking – Mixed Reality Portal can’t find your controllers. Hold them in front of your headset and restart them by pressing the **Windows** button for 4 seconds, then again for 2 seconds.
    * Low battery – Replace the controller batteries.
* If using Wi-Fi, try connecting your PC to a 5-GHz Wi-Fi network to reduce wireless interference. 
* For newer headsets that pair directly to the controllers, select the **“…”** button in **Mixed Reality Portal** and choose **Set up controllers**. This will take you to the headset app for pairing the controllers to the headset.  
* For older headsets that don’t have built-in Bluetooth for the controllers to pair directly:  
    * Select Settings  > Devices > Bluetooth & other devices on your PC and make sure the controllers are listed as paired. If they’re not, you’ll need to pair them. 
    * If you have other Bluetooth devices paired with your PC, such as headphones or gamepads, try removing some. Select **Settings > Devices > Bluetooth & other devices** on your PC, select the devices, and then select **Remove device**.
    * Remove Bluetooth headphones and speakers in **Settings > Devices > Bluetooth & other devices**, and turn off the devices. 
    * If you’re using a USB Bluetooth adapter, make sure it’s plugged into a black USB 2.0 port. Also make sure the adapter is plugged in as far away as possible from any other wireless transmitters or USB flash drives, including the USB connector for your headset. 
    * If your PC has built-in Bluetooth and you’re having connection problems, try using a USB Bluetooth adapter instead. (To do this, you’ll need to also turn off your built-in Bluetooth radio in [Device Manager](https://support.microsoft.com/help/4026149), and then pair your other Bluetooth devices with the new adapter.)
* If the Settings app is open to the Bluetooth & other devices page, close it.

## I’m experiencing discomfort when I use my headset

For general info about comfort in Windows Mixed Reality, see [Windows Mixed Reality immersive headset health, safety, and comfort](wmr-health-safety-comfort.md). For details about your specific headset, check with the headset manufacturer.

## My visuals are choppy, load slowly, or don’t look good

If your mixed reality visuals don’t look their best:

* Make sure your headset is plugged into the correct graphics card on your PC. Some PCs have both integrated and discrete graphics cards. The discrete card will generally provide the best performance. [Learn more about PC hardware](windows-mixed-reality-minimum-pc-hardware-compatibility-guidelines.md).
* Close unused apps on your desktop.
* Adjust your headset’s fit: move it lower and higher or left and right, and make sure it fits snugly.
* Adjust your headset's visual settings (**Settings > Mixed reality > Headset display**). When **Visual quality** is set to **Automatic**, we'll choose the best mixed reality experience for your PC. For an experience with more visual detail, set **Visual quality** to **High**. If your visuals are choppy, you may want to select a lower setting.
* Try adjusting your headset's calibration. The lenses should be adjusted to match your interpupillary distance (IPD), the distance between your pupils. If you don't know your IPD, an optometrist can measure it for you. There are also websites designed to measure IPD. Once you know your IPD, use your headset's calibration knob to make adjustments. If the headset doesn't have a calibration knob, select **Settings > Mixed reality > Headset display** and adjust the Calibration control.

## I have questions about my headset hardware

For details about your headset, check with the manufacturer. There may be a product guide in the box, or you can try the manufacturer’s website.

## The floor in mixed reality seems to be in the wrong spot

If the floor looks off (for example, you feel like you’re floating), select **Start > Room adjustment** while wearing your headset to make changes.

## I got a message that said to plug in and charge my PC. Why?

If you're using a laptop, Windows Mixed Reality works best when the PC is both fully charged and plugged in.

## How do I uninstall Windows Mixed Reality?

Select **Start > Settings > Mixed reality**, then select **Uninstall**. Make sure to disconnect your headset from your PC and close Mixed Reality Portal before uninstalling.

When you're ready to start using your headset again, plug it in, and Mixed Reality Portal will take you through setup.

> [!NOTE]
> If you see a message that says "We couldn't finish removing Windows Mixed Reality," this means that some files, including information about your environment, might still be on your computer. This can cause problems if you decide to reinstall Windows Mixed Reality later on.
> 
> To learn how to manually remove any remaining Windows Mixed Reality info from your PC, see **[this article](installation_errors.md)**.

## My Wi-Fi slows down when I'm using Windows Mixed Reality

If you're using a 2.4-GHz Wi-Fi connection, your motion controllers might slow down your Wi-Fi:

<!-- TODO: Use Windows Mixed Reality PC hardware guidelines interlink -->
* Switch to a 5-GHz Wi-Fi connection, if one is available. [Learn more](https://support.microsoft.com/help/4000461)
* Use a separate Bluetooth adapter to connect your motion controllers to your PC. [See recommended adapters](recommended-adapters-for-windows-mixed-reality-capable-pcs.md)

## What is the Experience options setting?

The Experience options setting (**Settings > Mixed reality > Headset display > Experience options**) gives you the ability to change the Windows Mixed Reality performance settings. This enables you to choose the best possible experience for your hardware configuration across a range of content. The 90-Hz experience is available to all systems, but you might want to try out Automatic first to see which setting you prefer.

Here are the options:

* Automatic or Let Windows decide: Windows Mixed Reality will determine the best experience for your hardware configuration. For most people, this is the best choice to start with.
* 60 Hz: Sets the refresh rate to 60 Hz and turns off certain features, such as video capture and preview in Mixed Reality Portal.
* 90 Hz: Sets the refresh rate to 90 Hz if your headset can run at that speed. If cable issues prevent the headset from running at 90 Hz, you may see an error at startup with this mode selected. 

## I see a message that says "Put on your headset" even though I have my headset on

When you put on your headset, Windows Mixed Reality needs a bit of time to reload your space. This can take a few seconds. If this message doesn't go away, make sure the protective sticker has been removed from the proximity sensor, which is on the inside of the headset, between the lenses. If the sticker has been removed and you're still having problems, contact your headset manufacturer. Pressing **Win+Y** on your keyboard will manually trigger the headset to run if the proximity sensor isn't triggering automatically. 

Still need help? For advanced troubleshooting, check out [this article](troubleshooting-windows-mixed-reality.md).

## See also

* [Ask the community](https://answers.microsoft.com)
* [Contact us for support](https://support.microsoft.com/contactus/)