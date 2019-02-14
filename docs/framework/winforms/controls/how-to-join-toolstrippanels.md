---
title: 如何：Join ToolStripPanels
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], joining together
- ToolStripPanel control [Windows Forms], joining together
ms.assetid: 4eadda6d-e3b8-4151-aaf2-a8d564fbe6b3
ms.openlocfilehash: cebfcb417dc011ed8990e9d536cd165c2a92cb68
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260733"
---
# <a name="how-to-join-toolstrippanels"></a>如何：Join ToolStripPanels
您可以在运行时将 <xref:System.Windows.Forms.ToolStrip> 控件联接到 <xref:System.Windows.Forms.ToolStripPanel>，它提供了多文档界面 (MDI) 应用程序的灵活性。  
  
## <a name="example"></a>示例  
 下列代码示例演示如何将 <xref:System.Windows.Forms.ToolStrip> 控件联接到 <xref:System.Windows.Forms.ToolStripPanel>。  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#11)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#11)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System.Design、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripPanel>
- [如何：MDI 中使用 Toolstrippanel](../../../../docs/framework/winforms/controls/how-to-use-toolstrippanels-for-mdi.md)
