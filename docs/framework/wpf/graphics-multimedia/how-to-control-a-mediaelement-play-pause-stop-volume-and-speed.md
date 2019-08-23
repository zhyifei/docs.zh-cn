---
title: 如何：控制 MediaElement（播放、暂停、停止、音量和速度）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930153"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>如何：控制 MediaElement（播放、暂停、停止、音量和速度）
下面的示例演示如何使用<xref:System.Windows.Controls.MediaElement>控制媒体的播放。 该示例创建了一个简单的 media player, 使你可以在媒体中播放、暂停、停止和向后跳过, 以及调整音量和速度比。  
  
## <a name="example"></a>示例  
 下面的代码创建 UI。  
  
> [!NOTE]
> `Manual`的<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 属性必须设置为,以便能够以交互方式停止、暂停和播放媒体。<xref:System.Windows.Controls.MediaElement>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>示例  
 下面的代码实现了示例 UI 控件的功能。 <xref:System.Windows.Controls.MediaElement.Play%2A>、和方法<xref:System.Windows.Controls.MediaElement.Stop%2A>用于分别播放、暂停和停止媒体。 <xref:System.Windows.Controls.MediaElement.Pause%2A> 通过更改的<xref:System.Windows.Controls.MediaElement> 属性,可以在媒体中跳过。<xref:System.Windows.Controls.MediaElement.Position%2A> 最后, <xref:System.Windows.Controls.MediaElement.Volume%2A>和<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>属性用于调整媒体的音量和播放速度。  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>请参阅

- [使用情节提要控制 MediaElement](how-to-control-a-mediaelement-by-using-a-storyboard.md)
