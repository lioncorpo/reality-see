---
title: Voice input in Unity
description: Learn how Unity exposes three ways to add voice input, speech recognition, and dictation to your Windows Mixed Reality application.
author: thetuvix
ms.author: alexturn
ms.date: 03/21/2018
ms.topic: article
keywords: Voice input, KeywordRecognizer, GrammarRecognizer, microphone, dictation, voice, mixed reality headset, windows mixed reality headset, virtual reality headset, MRTK, Mixed Reality Toolkit
---

# Voice input in Unity

>[!NOTE]
>Instead of the below information, consider using the Unity plug-in for the Cognitive Speech Services SDK which has much better Speech Accuracy results and provides easy access to speech-to-text decode and advanced speech features like dialog, intent based interaction, translation, text-to-speech synthesis and natural language speech recognition. Find the sample and documentaion here: https://docs.microsoft.com//azure/cognitive-services/speech-service/quickstart-csharp-unity   

Unity exposes three ways to add [Voice input](../../design/voice-input.md) to your Unity application.

With the KeywordRecognizer (one of two types of PhraseRecognizers), your app can be given an array of string commands to listen for. With the GrammarRecognizer (the other type of PhraseRecognizer), your app can be given an SRGS file defining a specific grammar to listen for. With the DictationRecognizer, your app can listen for any word and provide the user with a note or other display of their speech.

>[!NOTE]
>Only dictation or phrase recognition can be handled at once. That means if a GrammarRecognizer or KeywordRecognizer is active, a DictationRecognizer can not be active and vice versa.

## Enabling the capability for Voice

The **Microphone** capability must be declared for an app to use Voice input.
1. In the Unity Editor, go to the player settings by navigating to "Edit > Project Settings > Player"
2. Select on the "Windows Store" tab
3. In the "Publishing Settings > Capabilities" section, check the **Microphone** capability

## Phrase Recognition

To enable your app to listen for specific phrases spoken by the user then take some action, you need to:
1. Specify which phrases to listen for using a KeywordRecognizer or GrammarRecognizer
2. Handle the OnPhraseRecognized event and take action corresponding to the phrase recognized

### KeywordRecognizer

**Namespace:** *UnityEngine.Windows.Speech*<br>
**Types:** *KeywordRecognizer*, *PhraseRecognizedEventArgs*, *SpeechError*, *SpeechSystemStatus*

We'll need a few using statements to save some keystrokes:

```
using UnityEngine.Windows.Speech;
using System.Collections.Generic;
using System.Linq;
```

Then let's add a few fields to your class to store the recognizer and keyword->action dictionary:

```
KeywordRecognizer keywordRecognizer;
Dictionary<string, System.Action> keywords = new Dictionary<string, System.Action>();
```

Now add a keyword to the dictionary, for example in of a Start() method. We're adding the "activate" keyword in this example:

```
//Create keywords for keyword recognizer
keywords.Add("activate", () =>
{
    // action to be performed when this keyword is spoken
});
```

Create the keyword recognizer and tell it what we want to recognize:

```
keywordRecognizer = new KeywordRecognizer(keywords.Keys.ToArray());
```

Now register for the OnPhraseRecognized event

```
keywordRecognizer.OnPhraseRecognized += KeywordRecognizer_OnPhraseRecognized;
```

An example handler is:

```
private void KeywordRecognizer_OnPhraseRecognized(PhraseRecognizedEventArgs args)
{
    System.Action keywordAction;
    // if the keyword recognized is in our dictionary, call that Action.
    if (keywords.TryGetValue(args.text, out keywordAction))
    {
        keywordAction.Invoke();
    }
}
```

Finally, start recognizing!

```
keywordRecognizer.Start();
```

### GrammarRecognizer

**Namespace:** *UnityEngine.Windows.Speech*<br>
**Types**: *GrammarRecognizer*, *PhraseRecognizedEventArgs*, *SpeechError*, *SpeechSystemStatus*

The GrammarRecognizer is used if you're specifying your recognition grammar using SRGS. This can be useful if your app has more than just a few keywords, if you want to recognize more complex phrases, or if you want to easily turn on and off sets of commands. See: [Create Grammars Using SRGS XML](https://msdn.microsoft.com/library/hh378349(v=office.14).aspx) for file format information.

Once you have your SRGS grammar, and it is in your project in a [StreamingAssets folder](https://docs.unity3d.com/Manual/StreamingAssets.html):

```
<PROJECT_ROOT>/Assets/StreamingAssets/SRGS/myGrammar.xml
```

Create a GrammarRecognizer and pass it the path to your SRGS file:

```
private GrammarRecognizer grammarRecognizer;
grammarRecognizer = new GrammarRecognizer(Application.streamingDataPath + "/SRGS/myGrammar.xml");
```

Now register for the OnPhraseRecognized event

```
grammarRecognizer.OnPhraseRecognized += grammarRecognizer_OnPhraseRecognized;
```

You'll get a callback containing information specified in your SRGS grammar, which you can handle appropriately. Most of the important information will be provided in the semanticMeanings array.

```
private void Grammar_OnPhraseRecognized(PhraseRecognizedEventArgs args)
{
    SemanticMeaning[] meanings = args.semanticMeanings;
    // do something
}
```

Finally, start recognizing!

```
grammarRecognizer.Start();
```

## Dictation

**Namespace:** *UnityEngine.Windows.Speech*<br>
**Types**: *DictationRecognizer*, *SpeechError*, *SpeechSystemStatus*

Use the DictationRecognizer to convert the user's speech to text. The DictationRecognizer exposes [dictation](../../design/voice-input.md#dictation) functionality and supports registering and listening for hypothesis and phrase completed events, so you can give feedback to your user both while they speak and afterwards. Start() and Stop() methods respectively enable and disable dictation recognition. Once done with the recognizer, it should be disposed using Dispose() method to release the resources it uses. It will release these resources automatically during garbage collection at an additional performance cost if they aren't released before that.

There are only a few steps needed to get started with dictation:
1. Create a new DictationRecognizer
2. Handle Dictation events
3. Start the DictationRecognizer

### Enabling the capability for dictation

The "Internet Client" capability, along with the "Microphone" capability mentioned above, must be declared for an app to leverage dictation.
1. In the Unity Editor, go to the player settings by navigating to "Edit > Project Settings > Player" page
2. Select on the "Windows Store" tab
3. In the "Publishing Settings > Capabilities" section, check the **InternetClient** capability

### DictationRecognizer

Create a DictationRecognizer like so:

```
dictationRecognizer = new DictationRecognizer();
```

There are four dictation events that can be subscribed to and handled to implement dictation behavior.
1. DictationResult
2. DictationComplete
3. DictationHypothesis
4. DictationError

**DictationResult**

This event is fired after the user pauses, typically at the end of a sentence. The full recognized string is returned here.

First, subscribe to the DictationResult event:

```
dictationRecognizer.DictationResult += DictationRecognizer_DictationResult;
```

Then handle the DictationResult callback:

```
private void DictationRecognizer_DictationResult(string text, ConfidenceLevel confidence)
{
    // do something
}
```

**DictationHypothesis**

This event is fired continuously while the user is talking. As the recognizer listens, it provides text of what it's heard so far.

First, subscribe to the DictationHypothesis event:

```
dictationRecognizer.DictationHypothesis += DictationRecognizer_DictationHypothesis;
```

Then handle the DictationHypothesis callback:

```
private void DictationRecognizer_DictationHypothesis(string text)
{
    // do something
}
```

**DictationComplete**

This event is fired when the recognizer stops, whether from Stop() being called, a timeout occurring, or some other error.

First, subscribe to the DictationComplete event:

```
dictationRecognizer.DictationComplete += DictationRecognizer_DictationComplete;
```

Then handle the DictationComplete callback:

```
private void DictationRecognizer_DictationComplete(DictationCompletionCause cause)
{
   // do something
}
```

**DictationError**

This event is fired when an error occurs.

First, subscribe to the DictationError event:

```
dictationRecognizer.DictationError += DictationRecognizer_DictationError;
```

Then handle the DictationError callback:

```
private void DictationRecognizer_DictationError(string error, int hresult)
{
    // do something
}
```

Once you've subscribed and handled the dictation events that you care about, start the dictation recognizer to begin receiving events.

```
dictationRecognizer.Start();
```

If you no longer want to keep the DictationRecognizer around, you need to unsubscribe from the events and Dispose the DictationRecognizer.

```
dictationRecognizer.DictationResult -= DictationRecognizer_DictationResult;
dictationRecognizer.DictationComplete -= DictationRecognizer_DictationComplete ;
dictationRecognizer.DictationHypothesis -= DictationRecognizer_DictationHypothesis ;
dictationRecognizer.DictationError -= DictationRecognizer_DictationError ;
dictationRecognizer.Dispose();
```

**Tips**
* Start() and Stop() methods respectively enable and disable dictation recognition.
* Once done with the recognizer, it must be disposed using Dispose() method to release the resources it uses. It will release these resources automatically during garbage collection at an additional performance cost if they aren't released before that.
* Timeouts occur after a set period of time. You can check for these timeouts in the DictationComplete event. There are two timeouts to be aware of:
   1. If the recognizer starts and doesn't hear any audio for the first five seconds, it will time out.
   2. If the recognizer has given a result, but then hears silence for 20 seconds, it will time out.

## Using both Phrase Recognition and Dictation

If you want to use both phrase recognition and dictation in your app, you'll need to fully shut one down before you can start the other. If you have multiple KeywordRecognizers running, you can shut them all down at once with:

```
PhraseRecognitionSystem.Shutdown();
```

In order to restore all recognizers to their previous state, after the DictationRecognizer has stopped, you can call:

```
PhraseRecognitionSystem.Restart();
```

You could also just start a KeywordRecognizer, which will restart the PhraseRecognitionSystem as well.

## Using the microphone helper

The Mixed Reality Toolkit on GitHub contains a microphone helper class to hint at developers if there's a usable microphone on the system. One use for it's where one would want to check if there's microphone on system before showing any speech interaction hints in the application.

The microphone helper script can be found in the [Input/Scripts/Utilities folder](https://github.com/Microsoft/MixedRealityToolkit-Unity/blob/htk_release/Assets/HoloToolkit/Input/Scripts/Utilities/MicrophoneHelper.cs). The GitHub repo also contains a [small sample](https://github.com/Microsoft/MixedRealityToolkit-Unity/blob/htk_release/Assets/HoloToolkit-Examples/Input/Scripts/MicrophoneHelperSample.cs) demonstrating how to use the helper.

## Voice input in Mixed Reality Toolkit
You can find the examples of the voice input in this scene.

- [HoloToolkit-Examples/Input/Scenes/SpeechInputSource.unity](https://github.com/Microsoft/MixedRealityToolkit-Unity/blob/htk_release/Assets/HoloToolkit-Examples/Input/Scenes/SpeechInputSource.unity)

## Next Development Checkpoint

If you're following the Unity development checkpoint journey we've laid out, you're next task is exploring the Mixed Reality platform capabilities and APIs:

> [!div class="nextstepaction"]
> [Shared experiences](shared-experiences-in-unity.md)

You can always go back to the [Unity development checkpoints](unity-development-overview.md#2-core-building-blocks) at any time.
