---
title: 如何：使用 VideoDrawing 播放媒体
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956958"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>如何：使用 VideoDrawing 播放媒体
若要播放音频或视频文件, 请使用<xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>和。 加载并播放媒体有两种方法。 第一种方法是单独<xref:System.Windows.Media.MediaPlayer>使用<xref:System.Windows.Media.VideoDrawing>和, 第二种方法是创建您<xref:System.Windows.Media.MediaPlayer>自己<xref:System.Windows.Media.MediaTimeline>的以便与和<xref:System.Windows.Media.VideoDrawing>一起使用。  
  
> [!NOTE]
> 当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。 在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。  
  
## <a name="example"></a>示例  
 下面的示例使用<xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>和来播放视频文件一次。  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 若要获取对媒体的其他计时控制, 请<xref:System.Windows.Media.MediaTimeline>将<xref:System.Windows.Media.MediaPlayer>与和<xref:System.Windows.Media.VideoDrawing>对象一起使用。 <xref:System.Windows.Media.MediaTimeline>使您能够指定是否应重复视频。  
  
## <a name="example"></a>示例  
 下面的示例将<xref:System.Windows.Media.MediaTimeline> <xref:System.Windows.Media.MediaPlayer>和和<xref:System.Windows.Media.VideoDrawing>对象结合使用来反复播放视频。  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 请注意<xref:System.Windows.Media.MediaTimeline>, 当你使用时, 你将使用从<xref:System.Windows.Media.Animation.ClockController> <xref:System.Windows.Media.Animation.Clock.Controller%2A>的<xref:System.Windows.Media.MediaClock>属性返回的交互式来控制媒体播放, 而不是的交互式方法<xref:System.Windows.Media.MediaPlayer>。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Media.VideoDrawing>
- [Drawing 对象概述](drawing-objects-overview.md)
