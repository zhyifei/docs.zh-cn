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
ms.openlocfilehash: e9939c2d3d740bfe9296c23e47ef8ea09d837e01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498916"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="1aa03-102">如何：控制 MediaElement（播放、暂停、停止、音量和速度）</span><span class="sxs-lookup"><span data-stu-id="1aa03-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="1aa03-103">下面的示例演示如何控制播放的媒体使用<xref:System.Windows.Controls.MediaElement>。</span><span class="sxs-lookup"><span data-stu-id="1aa03-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="1aa03-104">该示例创建简单的媒体播放器，可用于播放、 暂停、 停止，请跳过在媒体中的往返，以及调整音量和速度比。</span><span class="sxs-lookup"><span data-stu-id="1aa03-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1aa03-105">示例</span><span class="sxs-lookup"><span data-stu-id="1aa03-105">Example</span></span>  
 <span data-ttu-id="1aa03-106">以下代码创建 UI。</span><span class="sxs-lookup"><span data-stu-id="1aa03-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1aa03-107"><xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>的属性<xref:System.Windows.Controls.MediaElement>必须设置为`Manual`以便能够以交互方式停止、 暂停和播放媒体。</span><span class="sxs-lookup"><span data-stu-id="1aa03-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="1aa03-108">示例</span><span class="sxs-lookup"><span data-stu-id="1aa03-108">Example</span></span>  
 <span data-ttu-id="1aa03-109">下面的代码实现的示例 UI 控件的功能。</span><span class="sxs-lookup"><span data-stu-id="1aa03-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="1aa03-110"><xref:System.Windows.Controls.MediaElement.Play%2A>， <xref:System.Windows.Controls.MediaElement.Pause%2A>，和<xref:System.Windows.Controls.MediaElement.Stop%2A>方法用于分别播放、 暂停和停止该媒体。</span><span class="sxs-lookup"><span data-stu-id="1aa03-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="1aa03-111">更改<xref:System.Windows.Controls.MediaElement.Position%2A>属性的<xref:System.Windows.Controls.MediaElement>可以跳过在媒体中。</span><span class="sxs-lookup"><span data-stu-id="1aa03-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="1aa03-112">最后，<xref:System.Windows.Controls.MediaElement.Volume%2A>和<xref:System.Windows.Controls.MediaElement.SpeedRatio%2A>属性用来调整媒体的音量和播放速度。</span><span class="sxs-lookup"><span data-stu-id="1aa03-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="1aa03-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="1aa03-113">See also</span></span>
- [<span data-ttu-id="1aa03-114">使用情节提要控制 MediaElement</span><span class="sxs-lookup"><span data-stu-id="1aa03-114">Control a MediaElement by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
