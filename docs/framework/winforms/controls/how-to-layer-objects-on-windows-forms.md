---
title: 如何：对 Windows 窗体上的对象分层
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
ms.openlocfilehash: 1a2a25f2e7eaa6618c0bf535a34f7dc6a28d51fa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533681"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>如何：对 Windows 窗体上的对象分层
当你创建复杂的用户界面，或使用多个文档界面 (MDI) 窗体时，你通常需要进行分层控件和子窗体上来创建更复杂的用户界面 (UI)。 若要移动并跟踪控件和 windows 组的上下文中的可操作其 z 顺序。 *Z 顺序*是沿窗体的 z 轴 （深度） 窗体上控件的可视化分层。 在 z 顺序的顶层窗口重叠所有其他窗口之上。 所有其他 windows 重叠窗口底部的 z 顺序。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。  
  
### <a name="to-layer-controls-at-design-time"></a>在设计时排列控件  
  
1.  选择你想要层的控件。  
  
2.  上**格式**菜单上，指向**顺序**，然后单击**置于顶层**或**置于底层**。  
  
### <a name="to-layer-controls-programmatically"></a>若要以编程方式对控件进行分层  
  
-   使用<xref:System.Windows.Forms.Control.BringToFront%2A>和<xref:System.Windows.Forms.Control.SendToBack%2A>操作控件的 z 顺序的方法。  
  
     例如，如果<xref:System.Windows.Forms.TextBox>控件， `txtFirstName`，是位于另一个控件，并且想要将其放在顶部，请使用以下代码：  
  
    ```vb  
    txtFirstName.BringToFront()  
    ```  
  
    ```csharp  
    txtFirstName.BringToFront();  
    ```  
  
    ```cpp  
    txtFirstName->BringToFront();  
    ```  
  
> [!NOTE]
>  Windows 窗体支持*控件包含*。 控件包含涉及放置多个在包含控件中，如大量的控件<xref:System.Windows.Forms.RadioButton>内控制<xref:System.Windows.Forms.GroupBox>控件。 然后可以层包含控件内的控件。 移动组框移动，这些控件，因为它们包含其内部。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
