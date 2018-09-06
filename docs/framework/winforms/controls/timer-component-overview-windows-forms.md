---
title: Timer 组件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 6e453f6b7718c6c5be3109f51153a3f5e4b5b6f4
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44032223"
---
# <a name="timer-component-overview-windows-forms"></a><span data-ttu-id="a0d09-102">Timer 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="a0d09-102">Timer Component Overview (Windows Forms)</span></span>
<span data-ttu-id="a0d09-103">Windows 窗体 <xref:System.Windows.Forms.Timer> 是一种按固定事件间隔引发事件的组件。</span><span class="sxs-lookup"><span data-stu-id="a0d09-103">The Windows Forms <xref:System.Windows.Forms.Timer> is a component that raises an event at regular intervals.</span></span> <span data-ttu-id="a0d09-104">此组件专为 Windows 窗体环境设计。</span><span class="sxs-lookup"><span data-stu-id="a0d09-104">This component is designed for a Windows Forms environment.</span></span> <span data-ttu-id="a0d09-105">如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。</span><span class="sxs-lookup"><span data-stu-id="a0d09-105">If you need a timer that is suitable for a server environment, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).</span></span>  
  
## <a name="key-properties-methods-and-events"></a><span data-ttu-id="a0d09-106">键属性、 方法和事件</span><span class="sxs-lookup"><span data-stu-id="a0d09-106">Key Properties, Methods, and Events</span></span>  
 <span data-ttu-id="a0d09-107">由定义的时间间隔长度<xref:System.Windows.Forms.Timer.Interval%2A>属性，其值是以毫秒为单位。</span><span class="sxs-lookup"><span data-stu-id="a0d09-107">The length of the intervals is defined by the <xref:System.Windows.Forms.Timer.Interval%2A> property, whose value is in milliseconds.</span></span> <span data-ttu-id="a0d09-108">启用了该组件，<xref:System.Windows.Forms.Timer.Tick>引发事件每个时间间隔。</span><span class="sxs-lookup"><span data-stu-id="a0d09-108">When the component is enabled, the <xref:System.Windows.Forms.Timer.Tick> event is raised every interval.</span></span> <span data-ttu-id="a0d09-109">这是将添加要执行的代码的位置。</span><span class="sxs-lookup"><span data-stu-id="a0d09-109">This is where you would add code to be executed.</span></span> <span data-ttu-id="a0d09-110">有关详细信息，请参阅[如何： 在使用 Windows 窗体 Timer 组件的设置时间间隔运行过程](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md)。</span><span class="sxs-lookup"><span data-stu-id="a0d09-110">For more information, see [How to: Run Procedures at Set Intervals with the Windows Forms Timer Component](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md).</span></span> <span data-ttu-id="a0d09-111">主要方法<xref:System.Windows.Forms.Timer>组件都<xref:System.Windows.Forms.Timer.Start%2A>和<xref:System.Windows.Forms.Timer.Stop%2A>，这将打开和关闭计时器。</span><span class="sxs-lookup"><span data-stu-id="a0d09-111">The key methods of the <xref:System.Windows.Forms.Timer> component are <xref:System.Windows.Forms.Timer.Start%2A> and <xref:System.Windows.Forms.Timer.Stop%2A>, which turn the timer on and off.</span></span> <span data-ttu-id="a0d09-112">关闭计时器时，它将重置;没有方法来暂停<xref:System.Windows.Forms.Timer>组件。</span><span class="sxs-lookup"><span data-stu-id="a0d09-112">When the timer is switched off, it resets; there is no way to pause a <xref:System.Windows.Forms.Timer> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d09-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d09-113">See Also</span></span>  
 <xref:System.Windows.Forms.Timer>  
 [<span data-ttu-id="a0d09-114">Timer 组件</span><span class="sxs-lookup"><span data-stu-id="a0d09-114">Timer Component</span></span>](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [<span data-ttu-id="a0d09-115">Windows 窗体 Timer 组件的 Interval 属性的限制</span><span class="sxs-lookup"><span data-stu-id="a0d09-115">Limitations of the Windows Forms Timer Component's Interval Property</span></span>](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
