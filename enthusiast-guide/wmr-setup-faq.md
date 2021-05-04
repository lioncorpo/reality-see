---
title: Windows Mixed Reality Setup FAQ
description: Get answers to common setup questions when working with Windows Mixed Reality applications and devices.
author: hferrone
ms.author: v-hferrone
ms.date: 09/15/2020
ms.topic: article
keywords: Windows Mixed Reality, Mixed Reality, Virtual Reality, VR, MR, Feedback, Feedback Hub, bugs
appliesto:
    - Windows 10
---

# Windows Mixed Reality Setup FAQ

Here’s some info to help troubleshoot problems you might run into when you set up your Windows Mixed Reality immersive headset.

## I get a message that says “We couldn’t download the Window Mixed Reality software,” or setup is stuck on the “Hang tight while we do some downloading” page

Try the following steps:

* Go to **Settings  > Update & security > Windows Update** and make sure Windows Update is turned on. Then, download and install any updates that are waiting to be installed.
* Make sure your PC is connected to the internet and has at least 2 GB of free storage space.
* Restart your PC and try again. You may need to repeat several times or run the Windows Update troubleshooter to clear pending updates.

> [!NOTE]
> * If you're on an enterprise managed network, check with your administrator. They might need to enable Windows Mixed Reality. Looking for the IT pro instructions? See **[this article](/windows/application-management/manage-windows-mixed-reality)**.
> * If your Wi-Fi network connection is set to metered, change it to unmetered. **[Learn more](https://support.microsoft.com/help/4028458)**

## I get a message that says "Something went wrong, and we couldn't start Windows Mixed Reality."

Try the following steps:

1. Unplug your headset from your computer (both cables).
2. Restart your computer.
3. Go **Settings  > Update & security > Windows Update** and make sure Windows Update is turned on. Then, download and install any updates that are waiting to be installed.
4. Reconnect your headset to the computer, then try setup again.

If the above steps don’t work, try uninstalling and then reinstalling Windows Mixed Reality. Go to **Settings  > Mixed reality > Uninstall** and select **Uninstall**. Then restart your computer. To start the setup process again, just plug your headset into your PC.

## The Mixed Reality Portal doesn’t open when I plug in my headset

Mixed Reality Portal, the app that takes you through Windows Mixed Reality setup, is designed to open automatically when you plug in a compatible headset. If it doesn’t open, go to Start and type "Mixed Reality Portal" in the Search box to open the app. You might need to [update to the latest version of Windows](https://support.microsoft.com/en-us/help/12373/windows-update-faq) if you can’t find the Mixed Reality Portal.

## I get a message that says my PC can’t run Windows Mixed Reality

If you get this message, your PC doesn’t meet the [minimum requirements](https://support.microsoft.com/help/4039260) needed to run Windows Mixed Reality. The computer’s hardware setup might not be compatible with Windows Mixed Reality, or you may need to [update to the latest version of Windows](https://support.microsoft.com/help/12373).

Notes on graphics cards:

* If Windows Mixed Reality setup says your graphics card doesn’t meet the requirements and you think it does, make sure your headset is plugged into the correct card.
* Check with your graphics card manufacturer for the latest driver update. Windows Mixed Reality requires a graphics card driver that supports at least WDDM 2.2.

## I get a message that says, “You’re nearly there—this PC doesn’t meet the minimum requirements needed to run Windows Mixed Reality.”

If you get this message, your PC doesn’t meet the minimum requirements needed for the best experience in Windows Mixed Reality. Your PC can run an immersive headset, but may not be able to run certain apps or might have problems with performance.

## My Xbox controller isn’t working

Try the following steps:

* Make sure your controller is turned on, fully charged, and connected to the PC.
* Replace the controller’s batteries.
* If you're using a Bluetooth controller, go to **Settings  > Devices > Bluetooth & other devices** on your PC and make sure it's paired (you should see it listed on the page).

[Learn more about Xbox controllers](https://support.xbox.com/xbox-on-windows/accessories/connect-xbox-one-controller-to-pc)

## My motion controllers aren't working

Try the following steps:

* Make sure your controllers are turned on and fully charged.
* Replace the controllers’ batteries.
* Turn the controllers off and on again while holding them in front of you. Press and hold the Windows  button for 4 seconds to turn off a controller, then press and hold it again for 2 seconds to turn it on.
* Go to **Settings  > Devices > Bluetooth & other devices** on your PC and make sure they’re paired (you should see them listed on the page).

[Learn more about motion controllers](controllers-in-wmr.md)

## I get a message that says, “Connect your headset” even though I’ve plugged in my headset

Try the following steps:

- Make sure your headset is connected to the correct ports on your computer. It should be plugged into the PC’s discrete graphics card and a USB 3.0 port. Here's how to identify the correct ports:
    - USB 3.0 ports have a special logo with an "SS" mark (indicating "SuperSpeed"). The port's inside piece is normally blue, but older USB 2.0 ports are typically black or white on the inside.
    - If your computer has two HDMI ports, use the one that connects to the graphics card, not the computer's motherboard. It's not always obvious, which is which, though discrete ports are often located in an expansion slot on the computer. If you try one port and it doesn't work, try the other.
- Go to the headset manufacturer’s website and update the drivers and firmware for your headset.

## During Mixed Reality start up, I'm stuck at "Turn your head side to side, and then at the floor"

This step lets your headset recognize your space and restore any existing virtual floor and boundary. When you put on your headset, this scanning process can take up to 10 seconds. After it's complete, you'll either be in Windows Mixed Reality home or you'll be prompted to set up your boundary again.

If the scanning process takes longer than 10 seconds, there could be a problem with the proximity sensor in the headset:

1. Check that the sticker has been removed from the proximity sensor. The proximity sensor is located inside the headset roughly where the center of your forehead would be.
2. Check that your proximity sensor is toggling input to your headset: with your finger, cover and uncover the proximity sensor a few times to verify input is switching to the headset. You should see the **Windows Key + Y** banner at the top of your PC. You can manually switch input to the headset at any time by typing **Windows Key + Y** on your keyboard.

## The floor of my Windows Mixed Reality home doesn't appear to be at the correct height

Select **Start > Floor Adjustment**, which will launch once you place the app in the world, to make changes while you're wearing the headset. In this app, you'll be directed to use the touch pad (motion controller) or direction pad (gamepad) to adjust the floor height. When the floor feels correct, use the Windows button to return to your home.

## I can't show a preview of what I'm seeing in my headset on my desktop

Windows Mixed Reality Portal has a **Play** button at the bottom of the screen that allows you to preview what you're seeing in your headset on your desktop screen. For performance reasons, this feature is only available on PCs running at Windows Mixed Reality Ultra (90 Hz).

## How can I get a clearer view in my headset

Try adjusting the fit of your headset. Adjust its position on your face by moving it up and down or left and right, and adjust the straps so it feels snug.

If your headset supports it, you can also adjust its calibration settings. If the headset has a knob to adjust calibration, use that. If it doesn’t, go to **Settings  > Mixed reality > Visual quality** and adjust the calibration there. For more information on calibration for your specific device, check with your headset manufacturer.

## When I plug in my headset, nothing happens—Mixed Reality Portal doesn’t open

Mixed Reality Portal, the app that takes you through Windows Mixed Reality setup, is designed to open automatically when you plug in a compatible headset. If it doesn’t open, go to **Start** and type **Mixed Reality Portal** in the **Search**  box to open the app from there. If you can’t find Mixed Reality Portal, that might mean you need to [update to the latest version of Windows](https://support.microsoft.com/help/12373) or that your headset isn't correctly connected to the PC.

## My head mount display doesn't work after I shut down and do a fast startup

Try this:

* Unplug the display cable and the USB cable from the head mount display and then plug them back in.

## My Wi-Fi slows down when I use Windows Mixed Reality

If you're using a 2.4-GHz Wi-Fi connection, your motion controllers might slow down your Wi-Fi. Try one of the following steps:

* Switch to a 5-GHz Wi-Fi connection, if one is available. Learn more
* Use a separate Bluetooth adapter to connect your motion controllers to your PC. [See recommended adapters](recommended-adapters-for-windows-mixed-reality-capable-pcs.md)

> [!NOTE]
> Newer headsets pair directly to the controllers through a built-in Bluetooth chip and shouldn’t experience this issue.

## I got a "Something went wrong" error message, or I'm having problems in the Mixed Reality Portal

To get more information about a specific error code, look [here](error-codes.md). You can also try to:

Restart Windows Mixed Reality:

1. Disconnect both headset cables from your PC.
2. Restart your PC.
3. Reconnect your headset.

Make sure that your PC recognizes your headset:

1. Select Start.
2. Type "Device Manager" in the search box and select it in the list.
3. Expand "Mixed reality devices" and see if your headset is listed.

If it isn't listed:

1. Plug the headset into different ports on the PC, if available.
2. Check for the latest software updates from Windows Update.
3. Uninstall and reinstall Windows Mixed Reality:
    1. Disconnect both headset cables from your PC.
    2. Select **Settings  > Mixed reality > Uninstall**.
    3. If your motion controllers are paired to your PC, select **Settings  > Devices  > Bluetooth & other devices** to unpair them. Select each controller, and "Remove device". If your controllers are paired to your headset, you can skip this step.
    4. Plug your headset back into your PC to reinstall Windows Mixed Reality.

## See also

* [Ask the community](https://answers.microsoft.com)
* [Contact us for support](https://support.microsoft.com/contactus/)
* [Troubleshooting](troubleshooting-windows-mixed-reality.md)