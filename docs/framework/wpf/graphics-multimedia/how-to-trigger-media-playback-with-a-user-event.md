---
title: "如何：使用用户事件来触发媒体播放功能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: aa93b757f0af38bc6b08d87ac5485e2bf0f45a1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="41e89-102">如何：使用用户事件来触发媒体播放功能</span><span class="sxs-lookup"><span data-stu-id="41e89-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="41e89-103">此示例演示如何将媒体播放与事件同步。</span><span class="sxs-lookup"><span data-stu-id="41e89-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e89-104">示例</span><span class="sxs-lookup"><span data-stu-id="41e89-104">Example</span></span>  
 <span data-ttu-id="41e89-105">下面的示例使用<xref:System.Windows.Controls.MediaElement>控件和<xref:System.Windows.Media.MediaTimeline>类播放声音，当用户单击时发生<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="41e89-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="41e89-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="41e89-106">See Also</span></span>  
 <xref:System.Windows.Controls.MediaElement>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.EventTrigger.RoutedEvent%2A>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 [<span data-ttu-id="41e89-107">帮助主题</span><span class="sxs-lookup"><span data-stu-id="41e89-107">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="41e89-108">图形和多媒体</span><span class="sxs-lookup"><span data-stu-id="41e89-108">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
