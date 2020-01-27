---
title: "\"计时器组件间隔\" 属性的限制"
ms.date: 03/30/2017
helpviewer_keywords:
- timers [Windows Forms], event intervals
- Interval property [Windows Forms], limitations
- timers [Windows Forms], Windows-based
- Timer component [Windows Forms], limitations of Interval property
ms.assetid: 7e5fb513-77e7-4046-a8e8-aab94e61ca0f
ms.openlocfilehash: 15626a53f0541ff79e2098377d9dfdb4626ac155
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745228"
---
# <a name="limitations-of-the-windows-forms-timer-components-interval-property"></a>Windows 窗体 Timer 组件的“间隔”属性的限制
Windows 窗体 <xref:System.Windows.Forms.Timer> 组件具有 <xref:System.Windows.Forms.Timer.Interval%2A> 属性，该属性指定一个计时器事件与下一个计时器事件之间的间隔时间（以毫秒为单位）。 除非禁用了该组件，否则计时器将继续按大致相等的时间间隔接收 <xref:System.Windows.Forms.Timer.Tick> 事件。  
  
 此组件专为 Windows 窗体环境设计。 如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。  
  
## <a name="the-interval-property"></a>Interval 属性  
 对 <xref:System.Windows.Forms.Timer> 组件进行编程时，<xref:System.Windows.Forms.Timer.Interval%2A> 属性有一些限制：  
  
- 如果你的应用程序或另一个应用程序对系统的需求（例如长循环、密集型计算或驱动器、网络或端口访问）发出大量要求，则在 <xref:System.Windows.Forms.Timer.Interval%2A> 属性指定的情况下，你的应用程序可能不会频繁地获取计时器事件。  
  
- 不保证时间间隔刚好在一段时间内。 为了确保准确性，计时器应根据需要检查系统时钟，而不是尝试跟踪内部累积的时间。  
  
- <xref:System.Windows.Forms.Timer.Interval%2A> 属性的精度以毫秒为单位。 某些计算机提供分辨率高于毫秒的高分辨率计数器。 此类计数器的可用性取决于计算机的处理器硬件。
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Timer>
- [Timer 组件](timer-component-windows-forms.md)
- [Timer 组件概述](timer-component-overview-windows-forms.md)
