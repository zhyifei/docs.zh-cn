---
title: 更改 ToolTip 组件的延迟
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746588"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>如何：更改 Windows 窗体 ToolTip 组件的延迟
可以为 Windows 窗体 <xref:System.Windows.Forms.ToolTip> 组件设置多个延迟值。 所有这些属性的度量单位是毫秒。 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 属性确定用户必须指向关联控件才能显示 ToolTip 字符串的时间长度。 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 属性设置当鼠标从与工具提示关联的控件移到另一控件时，后续工具提示字符串显示的毫秒数。 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 属性确定显示工具提示字符串的时间长度。 可以单独设置这些值，也可以通过设置 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 属性的值来设置这些值;其他延迟属性根据分配给 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 属性的值进行设置。 例如，将 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 设置为值 N 时，<xref:System.Windows.Forms.ToolTip.InitialDelay%2A> 设置为 N，<xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> 设置为 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 除以5（或 N/5）的值，并且 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> 设置为 <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> 属性（或5N）值的5倍的值。  
  
### <a name="to-set-the-delay"></a>设置延迟  
  
1. 设置以下属性，如本示例中所示。  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a>另请参阅

- [ToolTip 组件概述](tooltip-component-overview-windows-forms.md)
- [如何：在设计时设置 Windows 窗体控件的工具提示](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [ToolTip 组件](tooltip-component-windows-forms.md)
