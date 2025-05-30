---
title: "How to: Trigger Media Playback with a User Event"
description: Learn how to use the MediaElement control and the MediaTimeline class to trigger media playback with a user event.
ms.date: "03/30/2017"
ms.service: dotnet-framework
helpviewer_keywords:
  - "synchronizing media playback with events [WPF]"
  - "playback of media [WPF], synchronizing with events"
  - "media [WPF], synchronizing playback with events"
  - "multimedia [WPF], synchronizing media playback with events"
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
---
# How to: Trigger Media Playback with a User Event

This example shows how to synchronize media playback with an event.

## Example

The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.

[!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]

## See also

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [How-to Topics](audio-and-video-how-to-topics.md)
- [Graphics and Multimedia](index.md)
