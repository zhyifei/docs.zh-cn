---
title: "如何：控制 MediaElement（播放、暂停、停止、音量和速度）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7362c57afa3d5615ffaa0616823a954a2d577cfe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="47b6a-102">如何：控制 MediaElement（播放、暂停、停止、音量和速度）</span><span class="sxs-lookup"><span data-stu-id="47b6a-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="47b6a-103">下面的示例演示如何控制播放的媒体使用<xref:System.Windows.Controls.MediaElement>。</span><span class="sxs-lookup"><span data-stu-id="47b6a-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="47b6a-104">该示例创建简单的媒体播放，您可以播放、 暂停、 停止，并跳过在媒体中的来回以及调整卷和速度比。</span><span class="sxs-lookup"><span data-stu-id="47b6a-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47b6a-105">示例</span><span class="sxs-lookup"><span data-stu-id="47b6a-105">Example</span></span>  
 <span data-ttu-id="47b6a-106">下面的代码创建 UI。</span><span class="sxs-lookup"><span data-stu-id="47b6a-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47b6a-107"><xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>属性<xref:System.Windows.Controls.MediaElement>必须设置为`Manual`以便能够以交互方式停止、 暂停和播放媒体。</span><span class="sxs-lookup"><span data-stu-id="47b6a-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="47b6a-108">示例</span><span class="sxs-lookup"><span data-stu-id="47b6a-108">Example</span></span>  
 <span data-ttu-id="47b6a-109">下面的代码实现示例 UI 控件的功能。</span><span class="sxs-lookup"><span data-stu-id="47b6a-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="47b6a-110"><xref:System.Windows.Controls.MediaElement.Play%2A>， <xref:System.Windows.Controls.MediaElement.Pause%2A>，和<xref:System.Windows.Controls.MediaElement.Stop%2A>方法用于分别播放、 暂停和停止媒体。</span><span class="sxs-lookup"><span data-stu-id="47b6a-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="47b6a-111">更改<xref:System.Windows.Controls.MediaElement.Position%2A>属性<xref:System.Windows.Controls.MediaElement>允许你跳过在媒体中。</span><span class="sxs-lookup"><span data-stu-id="47b6a-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="47b6a-112">最后，<xref:System.Windows.Controls.MediaElement.Volume%2A>和<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>属性用于调整卷和播放媒体的速度。</span><span class="sxs-lookup"><span data-stu-id="47b6a-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="47b6a-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47b6a-113">See Also</span></span>  
 [<span data-ttu-id="47b6a-114">使用情节提要控制 MediaElement</span><span class="sxs-lookup"><span data-stu-id="47b6a-114">Control a MediaElement by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
