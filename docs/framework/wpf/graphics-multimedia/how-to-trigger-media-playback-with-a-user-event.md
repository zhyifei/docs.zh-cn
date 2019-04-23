---
title: 如何：使用用户事件触发媒体播放
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: ae8ba54cc852bb85350492c95e3e890aebf6534f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150171"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="5282c-102">如何：使用用户事件触发媒体播放</span><span class="sxs-lookup"><span data-stu-id="5282c-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="5282c-103">此示例演示如何将媒体播放与事件同步。</span><span class="sxs-lookup"><span data-stu-id="5282c-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5282c-104">示例</span><span class="sxs-lookup"><span data-stu-id="5282c-104">Example</span></span>  
 <span data-ttu-id="5282c-105">下面的示例使用<xref:System.Windows.Controls.MediaElement>控件和<xref:System.Windows.Media.MediaTimeline>类，以播放声音，当用户单击时发生<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="5282c-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="5282c-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="5282c-106">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="5282c-107">帮助主题</span><span class="sxs-lookup"><span data-stu-id="5282c-107">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="5282c-108">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="5282c-108">Graphics and Multimedia</span></span>](index.md)
