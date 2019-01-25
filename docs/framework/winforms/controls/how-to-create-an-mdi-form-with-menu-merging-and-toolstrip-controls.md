---
title: 如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStripPanel control [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
ms.assetid: 64992ed9-44af-4baf-b45f-863e6ab35711
ms.openlocfilehash: 6cbab3c588aa74809a7aef80ae6ffc4c3772069f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54646011"
---
# <a name="how-to-create-an-mdi-form-with-menu-merging-and-toolstrip-controls"></a>如何：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体
<xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间支持多文档界面 (MDI) 应用程序，而 <xref:System.Windows.Forms.MenuStrip> 控件支持菜单合并。 MDI 窗体还可支持 <xref:System.Windows.Forms.ToolStrip> 控件。  
  
 没有对此功能在 Visual Studio 中的广泛支持。  
  
 另请参阅[演练：创建具有菜单合并功能和 ToolStrip 控件的 MDI 窗体](walkthrough-creating-an-mdi-form-with-menu-merging-and-toolstrip-controls.md)。  
  
## <a name="example"></a>示例  
 以下代码示例演示如何将 <xref:System.Windows.Forms.ToolStripPanel> 控件和 MDI 窗体配合使用。 此窗体还支持菜单与子菜单合并。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.MdiForm#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.MdiForm/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此代码示例需要：  
  
-   对 System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。  另请参阅[如何：编译和运行完整的 Windows 窗体代码示例使用 Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅
- [ToolStrip 控件](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
