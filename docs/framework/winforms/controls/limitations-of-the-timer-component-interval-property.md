---
title: "限制的 Windows 窗体 Timer 组件 &#39; s 间隔属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec53957a61806239fdd41761de6e172681b7497b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="limitations-of-the-windows-forms-timer-component39s-interval-property"></a><span data-ttu-id="c09fe-102">限制的 Windows 窗体 Timer 组件 &#39; s 间隔属性</span><span class="sxs-lookup"><span data-stu-id="c09fe-102">Limitations of the Windows Forms Timer Component&#39;s Interval Property</span></span>
<span data-ttu-id="c09fe-103">Windows 窗体<xref:System.Windows.Forms.Timer>组件具有<xref:System.Windows.Forms.Timer.Interval%2A>属性，用于指定一个计时器事件和下一步之间传递的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="c09fe-103">The Windows Forms <xref:System.Windows.Forms.Timer> component has an <xref:System.Windows.Forms.Timer.Interval%2A> property that specifies the number of milliseconds that pass between one timer event and the next.</span></span> <span data-ttu-id="c09fe-104">除非禁用该组件，计时器会继续接收<xref:System.Windows.Forms.Timer.Tick>事件的大致相等的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c09fe-104">Unless the component is disabled, a timer continues to receive the <xref:System.Windows.Forms.Timer.Tick> event at roughly equal intervals of time.</span></span>  
  
 <span data-ttu-id="c09fe-105">此组件专为 Windows 窗体环境设计。</span><span class="sxs-lookup"><span data-stu-id="c09fe-105">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="c09fe-106">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。</span><span class="sxs-lookup"><span data-stu-id="c09fe-106">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="the-interval-property"></a><span data-ttu-id="c09fe-107">间隔属性</span><span class="sxs-lookup"><span data-stu-id="c09fe-107">The Interval Property</span></span>  
 <span data-ttu-id="c09fe-108"><xref:System.Windows.Forms.Timer.Interval%2A>属性具有几个限制要考虑进行编程时<xref:System.Windows.Forms.Timer>组件：</span><span class="sxs-lookup"><span data-stu-id="c09fe-108">The <xref:System.Windows.Forms.Timer.Interval%2A> property has a few limitations to consider when you are programming a <xref:System.Windows.Forms.Timer> component:</span></span>  
  
-   <span data-ttu-id="c09fe-109">如果你的应用程序或其他应用程序需求很大系统上-例如长循环、 密集型计算或驱动器、 网络或端口访问-你的应用程序可能无法获得的计时器事件，通常为<xref:System.Windows.Forms.Timer.Interval%2A>属性指定。</span><span class="sxs-lookup"><span data-stu-id="c09fe-109">If your application or another application is making heavy demands on the system — such as long loops, intensive calculations, or drive, network, or port access — your application may not get timer events as often as the <xref:System.Windows.Forms.Timer.Interval%2A> property specifies.</span></span>  
  
-   <span data-ttu-id="c09fe-110">不保证所精确经过的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c09fe-110">The interval is not guaranteed to elapse exactly on time.</span></span> <span data-ttu-id="c09fe-111">若要确保准确性，计时器应检查系统时钟根据需要而不是尝试内部跟踪的累积的时间。</span><span class="sxs-lookup"><span data-stu-id="c09fe-111">To ensure accuracy, the timer should check the system clock as needed, rather than try to keep track of accumulated time internally.</span></span>  
  
-   <span data-ttu-id="c09fe-112">精度<xref:System.Windows.Forms.Timer.Interval%2A>属性是以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="c09fe-112">The precision of the <xref:System.Windows.Forms.Timer.Interval%2A> property is in milliseconds.</span></span> <span data-ttu-id="c09fe-113">某些计算机提供的高分辨率的计数器，分辨率高于毫秒。</span><span class="sxs-lookup"><span data-stu-id="c09fe-113">Some computers provide a high-resolution counter that has a resolution higher than milliseconds.</span></span> <span data-ttu-id="c09fe-114">这种计数器的可用性取决于你的计算机的处理器硬件。</span><span class="sxs-lookup"><span data-stu-id="c09fe-114">The availability of such a counter depends on the processor hardware of your computer.</span></span> <span data-ttu-id="c09fe-115">有关详细信息，请参阅文章 172338，"如何为使用 QueryPerformanceCounter 到时间的代码，"http://support.microsoft.com 在 Microsoft 知识库。</span><span class="sxs-lookup"><span data-stu-id="c09fe-115">For more information, see article 172338, "How To Use QueryPerformanceCounter to Time Code," in the Microsoft Knowledge Base at http://support.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09fe-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c09fe-116">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="c09fe-117">Timer 组件</span><span class="sxs-lookup"><span data-stu-id="c09fe-117">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="c09fe-118">Timer 组件概述</span><span class="sxs-lookup"><span data-stu-id="c09fe-118">Timer Component Overview</span></span>](../../../../docs/framework/winforms/controls/timer-component-overview-windows-forms.md)
