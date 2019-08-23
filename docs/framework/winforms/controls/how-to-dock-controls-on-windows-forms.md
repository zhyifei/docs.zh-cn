---
title: 如何：在 Windows 窗体上停靠控件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], docking
- Explorer-style applications [Windows Forms], creating
- Windows Forms controls, filling client area
ms.assetid: bc11f2e4-e90a-4830-b0e2-f43b6e2b8bec
ms.openlocfilehash: dc514fd8b9b7a17bf07a878e42729db4187d2b82
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963630"
---
# <a name="how-to-dock-controls-on-windows-forms"></a>如何：在 Windows 窗体上停靠控件
您可以将控件停靠到窗体的边缘, 或者使控件填充控件的容器 (窗体或容器控件)。 例如, Windows 资源管理器将<xref:System.Windows.Forms.TreeView>其控件停靠在窗口的左侧, 并将<xref:System.Windows.Forms.ListView>其控件停靠到窗口的右侧。 使用所有<xref:System.Windows.Forms.Control.Dock%2A>可见 Windows 窗体控件的属性来定义停靠模式。  
  
> [!NOTE]
> 控件按 z 顺序反向停靠。  
  
 <xref:System.Windows.Forms.Control.Dock%2A> 属性<xref:System.Windows.Forms.Control.AutoSize%2A>与属性交互。 有关详细信息, 请参阅[AutoSize 属性概述](autosize-property-overview.md)。  
  
### <a name="to-dock-a-control"></a>停靠控件  
  
1. 选择要停靠的控件。  
  
2. 在属性窗口中, 单击<xref:System.Windows.Forms.Control.Dock%2A>属性右侧的箭头。  
  
     将显示一个编辑器, 其中显示一系列表示窗体边缘和中心的框。  
  
3. 单击表示要停靠控件的窗体边缘的按钮。 若要填充控件的窗体或容器控件的内容, 请单击中心框。 单击 " **(无)** " 以禁用停靠。  
  
     控件会自动调整控件的大小以适应停靠边缘的边界。  
  
    > [!NOTE]
    > 继承的控件必须`Protected`能够停靠。 若要更改控件的访问级别, 请在属性窗口中设置其**修饰符**属性。  
  
## <a name="see-also"></a>请参阅

- [Windows 窗体控件](index.md)
- [在 Windows 窗体上排列控件](arranging-controls-on-windows-forms.md)
- [标记各个 Windows 窗体控件并创建它们的快捷键](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
- [按功能列出的 Windows 窗体控件](windows-forms-controls-by-function.md)
- [如何：在 FlowLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [如何：在 TableLayoutPanel 控件中锚定和停靠子控件](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [AutoSize 属性概述](autosize-property-overview.md)
- [如何：Windows 窗体上的定位控件](how-to-anchor-controls-on-windows-forms.md)
