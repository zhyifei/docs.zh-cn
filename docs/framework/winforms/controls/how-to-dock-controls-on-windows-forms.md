---
title: "如何：在 Windows 窗体上停靠控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc7227ee46f127070b44771a56a89b82bd0930ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-dock-controls-on-windows-forms"></a>如何：在 Windows 窗体上停靠控件
你可以将控件停靠到窗体的边缘，或使它们填充控件的容器 （窗体或容器控件）。 例如，Windows 资源管理器停靠其<xref:System.Windows.Forms.TreeView>窗口左侧的控件并将其<xref:System.Windows.Forms.ListView>窗口的右侧的控件。 使用<xref:System.Windows.Forms.Control.Dock%2A>所有可见的 Windows 窗体控件来定义停靠模式的属性。  
  
> [!NOTE]
>  控件停靠在相反的 z 顺序。  
  
 <xref:System.Windows.Forms.Control.Dock%2A>属性与交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性。 有关详细信息，请参阅[AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)。  
  
### <a name="to-dock-a-control"></a>若要将控件停靠  
  
1.  选择你想要停靠的控件。  
  
2.  在属性窗口中，单击右侧的箭头<xref:System.Windows.Forms.Control.Dock%2A>属性。  
  
     显示一个编辑器，其中显示框的边缘和窗体的中心表示一系列。  
  
3.  单击表示你要将控件停靠的窗体的边缘的按钮。 若要填充的控件的窗体或容器控件的内容，单击中心框。 单击**（无）**禁用停靠。  
  
     控件自动调整大小以适合的停靠边缘的边界。  
  
    > [!NOTE]
    >  继承的控件必须`Protected`能够停靠。 若要更改控件的访问级别，设置其**修饰符**属性窗口中的属性。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [如何：在 FlowLayoutPanel 控件中锚定和停靠子控件](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)  
 [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](../../../../docs/framework/winforms/controls/how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)  
 [AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [如何：在 Windows 窗体上锚定控件](../../../../docs/framework/winforms/controls/how-to-anchor-controls-on-windows-forms.md)
