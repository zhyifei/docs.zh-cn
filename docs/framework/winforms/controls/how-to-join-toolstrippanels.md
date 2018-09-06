---
title: 如何：联接 ToolStripPanel
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: 5e1688fb00e6eefa4873284e1ea1ba29536d3227
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43878543"
---
# <a name="how-to-join-toolstrippanels"></a>如何：联接 ToolStripPanel
您可以在运行时将 <xref:System.Windows.Forms.ToolStrip> 控件联接到 <xref:System.Windows.Forms.ToolStripPanel>，它提供了多文档界面 (MDI) 应用程序的灵活性。  
  
## <a name="example"></a>示例  
 下列代码示例演示如何将 <xref:System.Windows.Forms.ToolStrip> 控件联接到 <xref:System.Windows.Forms.ToolStripPanel>。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 生成此示例的 visual Basic 或 Visual C# 命令行中的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。  另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripPanel>  
 [如何：在 MDI 中使用 ToolStripPanel](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
