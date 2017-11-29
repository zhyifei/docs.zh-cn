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
# <a name="timer-component-overview-windows-forms"></a>Timer 组件概述（Windows 窗体）
Windows 窗体 <xref:System.Windows.Forms.Timer> 是一种按固定事件间隔引发事件的组件。 此组件专为 Windows 窗体环境设计。 如果需要适合服务器环境的计时器，请参阅[基于服务器的计时器介绍](http://msdn.microsoft.com/en-us/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。  
  
## <a name="key-properties-methods-and-events"></a>键属性、 方法和事件  
 由定义的间隔长度<xref:System.Windows.Forms.Timer.Interval%2A>属性，其值为以毫秒为单位。 启用了该组件，<xref:System.Windows.Forms.Timer.Tick>引发事件每个时间间隔。 这是你将在其中添加代码以执行。 有关详细信息，请参阅[如何： 在使用 Windows 窗体计时器组件设置的间隔运行过程](../../../../docs/framework/winforms/controls/run-procedures-at-set-intervals-with-wf-timer-component.md)。 主要方法<xref:System.Windows.Forms.Timer>组件<xref:System.Windows.Forms.Timer.Start%2A>和<xref:System.Windows.Forms.Timer.Stop%2A>，这将计时器打开和关闭。 当计时器被禁用时，它将重置;没有方法来暂停<xref:System.Windows.Forms.Timer>组件。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.Timer>  
 [Timer 组件](../../../../docs/framework/winforms/controls/timer-component-windows-forms.md)  
 [Windows 窗体 Timer 组件的 Interval 属性的限制](../../../../docs/framework/winforms/controls/limitations-of-the-timer-component-interval-property.md)
