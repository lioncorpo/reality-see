---
title: Sharing object movements with multiple users
description: Complete this course to learn how to share object movements with multiple users in a HoloLens 2 application.
author: jessemcculloch
ms.author: jemccull
ms.date: 02/05/2021
ms.topic: article
keywords: mixed reality, unity, tutorial, hololens, multi-user capabilities, Photon, MRTK, mixed reality toolkit, UWP, Azure spatial anchors
ms.localizationpriority: high
---

# 4. Sharing object movements with multiple users

In this tutorial, you will learn how to share the movements of objects so that all participants of a shared experience can collaborate and view each other's interactions.

## Objectives

* Configure your project to share the movements of objects
* Learn how to build a basic multi-user collaborative app

## Preparing the scene

In this section, you will prepare the scene by adding the tutorial prefab.

In the Project window, navigate to the **Assets** > **MRTK.Tutorials.MultiUserCapabilities** > **Prefabs** folder and drag the **TableAnchor** prefab onto the **SharedPlayground** object in the Hierarchy window to add it to your scene as a child of the SharedPlayground object:

![Unity with newly added TableAnchor prefab selected](images/mr-learning-sharing/sharing-04-section1-step1-1.png)

## Configuring PUN to instantiate the objects

In this section, you will configure the project to use the Rover Explorer experience created during the [Getting started tutorials](mr-learning-base-01.md) and define where it will be instantiated.

In the Project window, navigate to the **Assets** > **MRTK.Tutorials.MultiUserCapabilities** > **Resources** folder.

In the Hierarchy window, expand the **NetworkLobby** object and select the **NetworkRoom** child object, then in the Inspector window, locate the **Photon Room (Script)** component and configure it as follows:

* To the **Rover Explorer Prefab** field, assign the **RoverExplorer_Complete_Variant** prefab from the Resources folder

![Unity with Photon Room component partially configured](images/mr-learning-sharing/sharing-04-section2-step1-1.png)

With the **NetworkRoom** child object still selected, in the Hierarchy window, expand the **TableAnchor** object, then in the Inspector window, locate the **Photon Room (Script)** component and configure it as follows:

* To the **Rover Explorer Location** field, assign the TableAnchor > **Table** child object from the Hierarchy window

![Unity with Photon Room component configured](images/mr-learning-sharing/sharing-04-section2-step1-2.png)

## Trying the experience with shared object movement

If you now build and deploy the Unity project to your HoloLens, and then, back in Unity, press the Play button to enter Game mode while the app is running on your HoloLens, you will see the object move in Unity when you move the object in HoloLens:

![Animation showing Unity with networked objects](images/mr-learning-sharing/sharing-04-section3-step1-1.gif)

## Congratulations

You have successfully configured your project to synchronize object movements so users can see the objects move when other users move them. In the next tutorial, you will implement functionality to align the experience in the physical world. This will ensure the users see each other in their actual physical location, and so the objects appear in the same physical position and rotation for all users.

> [!div class="nextstepaction"]
> [Next Tutorial: 5. Integrating Azure Spatial Anchors into a shared experience](mr-learning-sharing-05.md)
