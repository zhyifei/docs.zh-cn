---
title: Timer 组件概述
ms.date: 03/30/2017
f1_keywords:
- Timer
helpviewer_keywords:
- Timer component [Windows Forms], about Timer components
- timers [Windows Forms], about timers
ms.assetid: e672c05b-a8b6-4b26-9e4d-9223aa9e3873
ms.openlocfilehash: 83b52d395cdc3e3357bcf83517eab258a5c8ae08
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742781"
---
# <a name="timer-component-overview-windows-forms"></a>Timer 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Timer> 是一种按固定事件间隔引发事件的组件。 此组件专为 Windows 窗体环境设计。 如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。  
  
## <a name="key-properties-methods-and-events"></a>键属性、方法和事件  
 间隔的长度由 <xref:System.Windows.Forms.Timer.Interval%2A> 属性定义，该属性的值以毫秒为单位。 启用组件后，每个间隔引发 <xref:System.Windows.Forms.Timer.Tick> 事件。 这是要在其中添加要执行的代码的位置。 有关详细信息，请参阅[如何：按设置的时间间隔运行过程和 Windows 窗体定时器组件](run-procedures-at-set-intervals-with-wf-timer-component.md)。 <xref:System.Windows.Forms.Timer> 组件的关键方法 <xref:System.Windows.Forms.Timer.Start%2A> 和 <xref:System.Windows.Forms.Timer.Stop%2A>，这会打开和关闭计时器。 当计时器关闭时，它将重置;无法暂停 <xref:System.Windows.Forms.Timer> 组件。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.Timer>
- [Timer 组件](timer-component-windows-forms.md)
- [Windows 窗体 Timer 组件的 Interval 属性的限制](limitations-of-the-timer-component-interval-property.md)
