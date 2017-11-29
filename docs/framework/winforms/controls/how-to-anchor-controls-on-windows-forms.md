---
title: "如何：在 Windows 窗体上锚定控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Anchor property [Windows Forms], enabling resizable forms
- Windows Forms controls, screen resolutions
- resizing forms [Windows Forms]
- Windows Forms controls, size
- screen resolution and control display
- controls [Windows Forms], anchoring
- forms [Windows Forms], resizing
- Windows Forms, resizing
- controls [Windows Forms], positioning
ms.assetid: 59ea914f-fbd3-427a-80fe-decd02f7ae6d
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4c6f7cc527c7409ffecab2ac67386d0f819cce3e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-anchor-controls-on-windows-forms"></a>如何：在 Windows 窗体上锚定控件
如果您正在设计用户可以在运行时调整大小的窗体，你的窗体上的控件应调整大小和重新定位正确。 若要调整动态处理该窗体控件的大小，可以使用<xref:System.Windows.Forms.Control.Anchor%2A>Windows 窗体控件的属性。 <xref:System.Windows.Forms.Control.Anchor%2A>属性定义控件的定位点位置。 当控件定位到窗体和窗体调整时，控件将保持该控件的定位点位置之间的距离。 例如，如果你有<xref:System.Windows.Forms.TextBox>调整窗体的大小时，定位到的左侧、 右侧和底部边缘该窗体的控件<xref:System.Windows.Forms.TextBox>水平控件调整，以便它维护窗体左右两侧距离相同。 此外，该控件垂直定位其自身，以便其位置总是与窗体的下边缘的距离相同。 如果控件不锚定和窗体调整，则更改相对于边缘的窗体控件的位置。  
  
 <xref:System.Windows.Forms.Control.Anchor%2A>属性与交互<xref:System.Windows.Forms.Control.AutoSize%2A>属性。 有关详细信息，请参阅[AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-anchor-a-control-on-a-form"></a>若要锚定窗体上控件  
  
1.  选择你想要定位的控件。  
  
    > [!NOTE]
    >  您可以通过按住 CTRL 键，单击以选中它，每个控件，然后按照此过程的其余部分同时定位多个控件。  
  
2.  在**属性**窗口中，单击右侧的箭头<xref:System.Windows.Forms.Control.Anchor%2A>属性。  
  
     编辑器，显示一个十字线显示。  
  
3.  若要设置定位点，请单击上、 左、 右或该十字线的下半部分。  
  
     控件定位到顶部，并且默认情况下保留。  
  
4.  若要清除已锚定的控件的一侧，请单击跨该 arm。  
  
5.  若要关闭<xref:System.Windows.Forms.Control.Anchor%2A>属性编辑器中，单击<xref:System.Windows.Forms.Control.Anchor%2A>再次属性名称。  
  
 当在运行时显示窗体时，控件将调整大小以保持与窗体的边缘的距离相同不变。 锚定的边缘的距离一直保持所定义时在 Windows 窗体设计器中放置控件的距离。  
  
> [!NOTE]
>  某些控件，如<xref:System.Windows.Forms.ComboBox>控件中，具有其高度的限制。 锚定到底部其窗体或容器的控件不能强制该控件超过其高度限制。  
  
 继承的控件必须`Protected`能够进行定位。 若要更改控件的访问级别，设置其`Modifiers`中的属性**属性**窗口。  
  
## <a name="see-also"></a>另请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [AutoSize 属性概述](../../../../docs/framework/winforms/controls/autosize-property-overview.md)  
 [如何：在 Windows 窗体上停靠控件](../../../../docs/framework/winforms/controls/how-to-dock-controls-on-windows-forms.md)  
 [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [演练：使用 Padding、Margins 和 AutoSize 属性对 Windows 窗体控件进行布局](../../../../docs/framework/winforms/controls/windows-forms-controls-padding-autosize.md)
