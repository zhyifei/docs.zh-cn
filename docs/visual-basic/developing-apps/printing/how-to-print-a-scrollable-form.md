---
title: 如何：打印可滚动的窗体 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- entire form [Visual Basic], printing
- scrollable form [Visual Basic], printing
ms.assetid: 1196e1cf-b77f-4928-a3e4-85b51ba3787d
ms.openlocfilehash: 4a509b7c48f2bff705bc95e58fb88252cb8ca4b9
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43532652"
---
# <a name="how-to-print-a-scrollable-form-visual-basic"></a>如何：打印可滚动的窗体 (Visual Basic)
通过 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件，可以在不使用 <xref:System.Drawing.Printing.PrintDocument> 组件的情况下快速打印窗体的图像。 默认情况下，只打印窗体当前可见部分；如果用户在运行时调整了窗体的大小，则可能无法按预期打印图像。 下面的过程演示如何打印可滚动窗体的完整工作区，即使已调整该窗体大小。  
  
 在 Visual Studio 中，不再包含 PowerPack 控件，但您可以下载它们从[下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=25169)。  
  
### <a name="to-print-the-complete-client-area-of-a-scrollable-form"></a>打印可滚动窗体的完整工作区  
  
1.  在“工具箱” 中，单击“Visual Basic PowerPacks”  选项卡，然后将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件拖动到窗体上。  
  
     <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm> 组件将添加到组件栏。  
  
2.  在“属性”  窗口中，将 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A> 属性设置为 <xref:System.Drawing.Printing.PrintAction.PrintToPrinter>。  
  
3.  在相应的事件处理程序中（例如在“打印” `Click`**的**`Button`事件处理程序中）添加以下代码。  
  
    ```  
    PrintForm1.Print(Me, PowerPacks.Printing.PrintForm.PrintOption.Scrollable)  
    ```  
  
    > [!NOTE]
    >  在某些操作系统上，通过 <xref:System.Drawing.Graphics> 方法绘制的文本或图形可能无法正确打印。 在这种情况下，你将无法使用 `Scrollable` 参数进行打印。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.PrintAction%2A>  
 <xref:Microsoft.VisualBasic.PowerPacks.Printing.PrintForm.Print%2A>  
 [PrintForm 组件](../../../visual-basic/developing-apps/printing/printform-component.md)  
 [如何：打印窗体的工作区](../../../visual-basic/developing-apps/printing/how-to-print-the-client-area-of-a-form.md)  
 [如何：打印窗体的工作区和非工作区](../../../visual-basic/developing-apps/printing/how-to-print-client-and-non-client-areas-of-a-form.md)
