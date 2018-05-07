---
title: 如何：在 Windows 窗体上定位控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Location
- Location.Y
- Location.X
helpviewer_keywords:
- controls [Windows Forms]
- controls [Windows Forms], moving
- snaplines
- controls [Windows Forms], positioning
ms.assetid: 4693977e-34a4-4f19-8221-68c3120c2b2b
ms.openlocfilehash: 6db021f2b1a29c3ef52a182c45bbc7878feebb97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-position-controls-on-windows-forms"></a>如何：在 Windows 窗体上定位控件
若要放置控件，请使用 Windows 窗体设计器中，或指定<xref:System.Windows.Forms.Control.Location%2A>属性。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-position-a-control-on-the-design-surface-of-the-windows-forms-designer"></a>若要在 Windows 窗体设计器的设计图面上将控件放  
  
-   将控件拖到使用鼠标的适当位置。  
  
    > [!NOTE]
    >  选择控件，并移动它带有箭头键以更精确地放置。 此外，*对齐线*有助于在你的窗体上精确地放置控件。 有关详细信息，请参阅[演练： 在 Windows 窗体使用对齐线上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)。  
  
### <a name="to-position-a-control-using-the-properties-window"></a>若要使用属性窗口将控件放  
  
1.  单击你想要定位的控件。  
  
2.  在**属性**窗口中，类型值<xref:System.Windows.Forms.Control.Location%2A>属性，使用逗号分隔，以定位该控件在其容器内的。  
  
     第一个数字 (X) 是从容器; 的左边框的距离第二个数字 (Y) 是从上边界的容器区域中，以像素为单位的距离。  
  
    > [!NOTE]
    >  你可以展开<xref:System.Windows.Forms.Control.Location%2A>属性键入**X**和**Y**单独值。  
  
### <a name="to-position-a-control-programmatically"></a>以编程方式定位控件  
  
1.  设置<xref:System.Windows.Forms.Control.Location%2A>该控件的属性<xref:System.Drawing.Point>。  
  
    ```vb  
    Button1.Location = New Point(100, 100)  
    ```  
  
    ```csharp  
    button1.Location = new Point(100, 100);  
    ```  
  
    ```cpp  
    button1->Location = Point(100, 100);  
    ```  
  
2.  更改控件的位置的 X 坐标使用<xref:System.Windows.Forms.Control.Left%2A>子属性。  
  
    ```vb  
    Button1.Left = 300  
    ```  
  
    ```csharp  
    button1.Left = 300;  
    ```  
  
    ```cpp  
    button1->Left = 300;  
    ```  
  
### <a name="to-increment-a-controls-location-programmatically"></a>若要以编程方式递增控件的位置  
  
1.  设置<xref:System.Windows.Forms.Control.Left%2A>子属性可增加该控件的 X 坐标。  
  
    ```vb  
    Button1.Left += 200  
    ```  
  
    ```csharp  
    button1.Left += 200;  
    ```  
  
    ```cpp  
    button1->Left += 200;  
    ```  
  
    > [!NOTE]
    >  使用<xref:System.Windows.Forms.Control.Location%2A>属性来设置控件的 X 和 Y 将同时定位。 若要单独设置位置，请使用控件的<xref:System.Windows.Forms.Control.Left%2A>(**X**) 或<xref:System.Windows.Forms.Control.Top%2A>(**Y**) 子属性。 不要尝试隐式设置的 X 和 Y 坐标<xref:System.Drawing.Point>结构，它表示该按钮的位置，因为此结构包含按钮的坐标的副本。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [演练：使用对齐线在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-snaplines.md)  
 [演练：使用 TableLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)  
 [演练：使用 FlowLayoutPanel 在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)  
 [如何： 设置 Windows 窗体的屏幕位置](http://msdn.microsoft.com/library/cb023ab7-dea7-4284-9aa6-8c03c59b60c6)
