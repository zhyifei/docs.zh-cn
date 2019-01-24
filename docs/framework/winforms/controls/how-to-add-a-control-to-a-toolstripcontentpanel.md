---
title: 如何：向 ToolStripContentPanel 添加控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStripContentPanel [Windows Forms], adding controls
ms.assetid: fa410960-bf1a-42fc-80e8-f2e27fb3dbb8
ms.openlocfilehash: 646451be26e8e6e833b9b204aee722aa3e8a5666
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584657"
---
# <a name="how-to-add-a-control-to-a-toolstripcontentpanel"></a>如何：向 ToolStripContentPanel 添加控件
可通过编程方式向 <xref:System.Windows.Forms.ToolStripContentPanel> 添加一个或多个控件。  
  
## <a name="example"></a>示例  
 下面的代码示例演示如何将 <xref:System.Windows.Forms.RichTextBox> 添加到 <xref:System.Windows.Forms.ToolStripContentPanel>。  
  
 [!code-csharp[System.Windows.Forms.ToolStripContainer#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStripContainer/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStripContainer#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStripContainer/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此代码示例需要：  
  
-   引用 System、System.Data 和 System.Windows.Forms 程序集。  
  
 Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。  另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))或[ToolStripContainer 任务对话框](https://msdn.microsoft.com/library/ms233647\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.ToolStripContentPanel>
- <xref:System.Windows.Forms.ToolStripContainer>
- [ToolStripContainer 控件](../../../../docs/framework/winforms/controls/toolstripcontainer-control.md)
- [ToolStrip 控件](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
