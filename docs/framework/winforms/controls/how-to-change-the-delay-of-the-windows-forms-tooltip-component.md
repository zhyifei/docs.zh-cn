---
title: "如何：更改 Windows 窗体 ToolTip 组件的延迟"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f8506df062729a98adc1aa1e0dcb524aa4ec812c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a>如何：更改 Windows 窗体 ToolTip 组件的延迟
有多个可以设置为 Windows 窗体的延迟值<xref:System.Windows.Forms.ToolTip>组件。 所有这些属性的度量单位为毫秒。 <xref:System.Windows.Forms.ToolTip.InitialDelay%2A>属性确定多长时间，用户必须指向要显示的工具提示字符串的关联控件。 <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>属性设置的后续工具提示字符串出现鼠标从一个工具提示关联的控件移到另一个所需的毫秒数。 <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>属性确定的工具提示字符串会显示的时间长度。 你可以单独进行，或通过设置的值设置这些值<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>属性; 其他属性根据分配给的值设置的延迟<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>属性。 例如，当<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>设置为的值为 N，<xref:System.Windows.Forms.ToolTip.InitialDelay%2A>设置为 N，<xref:System.Windows.Forms.ToolTip.ReshowDelay%2A>设置的值为<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>除以 5 （或 N/5），和<xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A>设置一个值，是五次的值为<xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>属性 （即 5N）。  
  
### <a name="to-set-the-delay"></a>若要设置延迟  
  
1.  在此示例中所示，请设置以下属性。  
  
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
  
## <a name="see-also"></a>请参阅  
 [ToolTip 组件概述](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)  
 [如何：在设计时设置 Windows 窗体控件的工具提示](../../../../docs/framework/winforms/controls/how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)  
 [ToolTip 组件](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
