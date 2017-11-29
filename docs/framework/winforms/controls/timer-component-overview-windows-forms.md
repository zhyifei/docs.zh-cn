---
title: "Timer 组件概述（Windows 窗体）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ea78cadae6e033bc54274e5428ba5e8c6410259d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="f4b9d-102">Timer 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="f4b9d-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="f4b9d-103">Windows 窗体 <xref:System.Windows.Forms.Timer> 是一种按固定事件间隔引发事件的组件。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="f4b9d-104">此组件专为 Windows 窗体环境设计。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="f4b9d-105">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="f4b9d-106">键属性、 方法和事件</span><span class="sxs-lookup"><span data-stu-id="f4b9d-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="f4b9d-107">由定义的间隔长度<xref:System.Windows.Forms.Timer.Interval%2A>属性，其值为以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="f4b9d-108">启用了该组件，<xref:System.Windows.Forms.Timer.Tick>引发事件每个时间间隔。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="f4b9d-109">这是你将在其中添加代码以执行。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="f4b9d-110">有关详细信息，请参阅[如何： 在使用 Windows 窗体计时器组件设置的间隔运行过程](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="f4b9d-111">主要方法<xref:System.Windows.Forms.Timer>组件<xref:System.Windows.Forms.Timer.Start%2A>和<xref:System.Windows.Forms.Timer.Stop%2A>，这将计时器打开和关闭。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="f4b9d-112">当计时器被禁用时，它将重置;没有方法来暂停<xref:System.Windows.Forms.Timer>组件。</span><span class="sxs-lookup"><span data-stu-id="f4b9d-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b9d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f4b9d-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="f4b9d-114">Timer 组件</span><span class="sxs-lookup"><span data-stu-id="f4b9d-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="f4b9d-115">Windows 窗体 Timer 组件的 Interval 属性的限制</span><span class="sxs-lookup"><span data-stu-id="f4b9d-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
