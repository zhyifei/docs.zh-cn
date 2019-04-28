---
title: 如何：使用 VideoDrawing 播放媒体
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61926060"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="fabe9-102">如何：使用 VideoDrawing 播放媒体</span><span class="sxs-lookup"><span data-stu-id="fabe9-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="fabe9-103">若要播放音频或视频文件，请使用<xref:System.Windows.Media.VideoDrawing>和一个<xref:System.Windows.Media.MediaPlayer>。</span><span class="sxs-lookup"><span data-stu-id="fabe9-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="fabe9-104">加载并播放媒体有两种方法。</span><span class="sxs-lookup"><span data-stu-id="fabe9-104">There are two ways to load and play media.</span></span> <span data-ttu-id="fabe9-105">第一种是使用<xref:System.Windows.Media.MediaPlayer>和一个<xref:System.Windows.Media.VideoDrawing>通过本身，第二个方法是创建您自己<xref:System.Windows.Media.MediaTimeline>要用于<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>。</span><span class="sxs-lookup"><span data-stu-id="fabe9-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fabe9-106">当媒体随应用程序一起分发时，无法像图像那样将媒体文件用作项目资源。</span><span class="sxs-lookup"><span data-stu-id="fabe9-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="fabe9-107">在项目文件中，必须改为将媒体类型设置为 `Content` 并将 `CopyToOutputDirectory` 设置为 `PreserveNewest` 或 `Always`。</span><span class="sxs-lookup"><span data-stu-id="fabe9-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fabe9-108">示例</span><span class="sxs-lookup"><span data-stu-id="fabe9-108">Example</span></span>  
 <span data-ttu-id="fabe9-109">下面的示例使用<xref:System.Windows.Media.VideoDrawing>和一个<xref:System.Windows.Media.MediaPlayer>播放视频文件一次。</span><span class="sxs-lookup"><span data-stu-id="fabe9-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="fabe9-110">若要获得对媒体的额外计时控制，请使用<xref:System.Windows.Media.MediaTimeline>与<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>对象。</span><span class="sxs-lookup"><span data-stu-id="fabe9-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="fabe9-111"><xref:System.Windows.Media.MediaTimeline>使您能够指定是否应重复显示视频。</span><span class="sxs-lookup"><span data-stu-id="fabe9-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fabe9-112">示例</span><span class="sxs-lookup"><span data-stu-id="fabe9-112">Example</span></span>  
 <span data-ttu-id="fabe9-113">下面的示例使用<xref:System.Windows.Media.MediaTimeline>与<xref:System.Windows.Media.MediaPlayer>和<xref:System.Windows.Media.VideoDrawing>要重复播放视频的对象。</span><span class="sxs-lookup"><span data-stu-id="fabe9-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="fabe9-114">请注意，当您使用<xref:System.Windows.Media.MediaTimeline>，使用交互式<xref:System.Windows.Media.Animation.ClockController>从返回<xref:System.Windows.Media.Animation.Clock.Controller%2A>属性<xref:System.Windows.Media.MediaClock>而不是交互式的方法控制媒体播放<xref:System.Windows.Media.MediaPlayer>。</span><span class="sxs-lookup"><span data-stu-id="fabe9-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fabe9-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fabe9-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="fabe9-116">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="fabe9-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
