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
ms.openlocfilehash: d67d9b204c316dce5f3818496d791ed4c1b352f2
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44249109"
---
# <a name="how-to-layer-objects-on-windows-forms"></a>如何：对 Windows 窗体上的对象分层
当您创建复杂的用户界面，或使用多文档界面 (MDI) 窗体时，通常想要层控件和子窗体以创建更复杂的用户界面 (UI)。 若要移动跟踪的控件和 windows 组的上下文中，可操作其 z 顺序。 *Z 顺序*是沿窗体的 z 轴 （深度） 窗体上控件的可视化分层。 在窗口顶部的 z 顺序重叠所有其他窗口之上。 所有其他窗口重叠窗口底部的 z 顺序。  
  
> [!NOTE]
>  显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。 若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。 有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。  
  
### <a name="to-layer-controls-at-design-time"></a>在设计时排列控件  
  
1.  选择你想要层的控件。  
  
2.  上**格式**菜单，依次指向**顺序**，然后单击**置于顶层**或者**发送回**。  
  
### <a name="to-layer-controls-programmatically"></a>若要以编程方式对控件进行分层  
  
-   使用<xref:System.Windows.Forms.Control.BringToFront%2A>和<xref:System.Windows.Forms.Control.SendToBack%2A>操作控件的 z 顺序的方法。  
  
     例如，如果<xref:System.Windows.Forms.TextBox>控件， `txtFirstName`，是其下方另一个控件，并想要将其放在顶部，请使用以下代码：  
  
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
>  Windows 窗体支持*控件包含*。 控件包含涉及到将放置多个控件内包含的控件，例如的数目<xref:System.Windows.Forms.RadioButton>控件的<xref:System.Windows.Forms.GroupBox>控件。 然后可以层中包含的控件的控件。 移动分组框移动，这些控件，因为它们包含其内部。  
  
## <a name="see-also"></a>请参阅  
 [Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)  
 [在 Windows 窗体上排列控件](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [标记各个 Windows 窗体控件并创建它们的快捷键](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [在 Windows 窗体上使用的控件](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [按功能列出的 Windows 窗体控件](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
