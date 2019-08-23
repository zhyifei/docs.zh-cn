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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="39598-102">如何：控制 MediaElement（播放、暂停、停止、音量和速度）</span><span class="sxs-lookup"><span data-stu-id="39598-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="39598-103">下面的示例演示如何使用<xref:System.Windows.Controls.MediaElement>控制媒体的播放。</span><span class="sxs-lookup"><span data-stu-id="39598-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="39598-104">该示例创建了一个简单的 media player, 使你可以在媒体中播放、暂停、停止和向后跳过, 以及调整音量和速度比。</span><span class="sxs-lookup"><span data-stu-id="39598-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39598-105">示例</span><span class="sxs-lookup"><span data-stu-id="39598-105">Example</span></span>  
 <span data-ttu-id="39598-106">下面的代码创建 UI。</span><span class="sxs-lookup"><span data-stu-id="39598-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="39598-107">`Manual`的<xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> 属性必须设置为,以便能够以交互方式停止、暂停和播放媒体。<xref:System.Windows.Controls.MediaElement></span><span class="sxs-lookup"><span data-stu-id="39598-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="39598-108">示例</span><span class="sxs-lookup"><span data-stu-id="39598-108">Example</span></span>  
 <span data-ttu-id="39598-109">下面的代码实现了示例 UI 控件的功能。</span><span class="sxs-lookup"><span data-stu-id="39598-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="39598-110"><xref:System.Windows.Controls.MediaElement.Play%2A>、和方法<xref:System.Windows.Controls.MediaElement.Stop%2A>用于分别播放、暂停和停止媒体。 <xref:System.Windows.Controls.MediaElement.Pause%2A></span><span class="sxs-lookup"><span data-stu-id="39598-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="39598-111">通过更改的<xref:System.Windows.Controls.MediaElement> 属性,可以在媒体中跳过。<xref:System.Windows.Controls.MediaElement.Position%2A></span><span class="sxs-lookup"><span data-stu-id="39598-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="39598-112">最后, <xref:System.Windows.Controls.MediaElement.Volume%2A>和<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>属性用于调整媒体的音量和播放速度。</span><span class="sxs-lookup"><span data-stu-id="39598-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="39598-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="39598-113">See also</span></span>

- [<span data-ttu-id="39598-114">使用情节提要控制 MediaElement</span><span class="sxs-lookup"><span data-stu-id="39598-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
