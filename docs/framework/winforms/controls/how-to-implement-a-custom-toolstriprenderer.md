---
title: 如何：实现自定义 ToolStripRenderer
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolStrip control [Windows Forms]
ms.assetid: c66fd3f7-2377-4553-8f1b-006527f08f32
ms.openlocfilehash: acf5967c015d61a0cc148e5cb509a5a7ded2152c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533193"
---
# <a name="how-to-implement-a-custom-toolstriprenderer"></a>如何：实现自定义 ToolStripRenderer
可以通过实现从 <xref:System.Windows.Forms.ToolStripRenderer> 中派生的类来自定义 <xref:System.Windows.Forms.ToolStrip> 控件的外观。 这使你可以灵活地创建一个不同于 <xref:System.Windows.Forms.ToolStripProfessionalRenderer> 类和 <xref:System.Windows.Forms.ToolStripSystemRenderer> 类提供的外观的外观。  
  
## <a name="example"></a>示例  
 以下代码示例演示了如何实现一个自定义 <xref:System.Windows.Forms.ToolStripRenderer> 类。 在此示例中，`GridStrip` 控件实现了一个滑动磁贴拼图，这样用户就可以在表布局中移动磁贴，以形成图像。 某个自定义 <xref:System.Windows.Forms.ToolStrip> 控件在网格布局中排列其 <xref:System.Windows.Forms.ToolStripButton> 控件。 布局包含一个空单元格，用户可以通过拖放操作，将相邻的磁贴滑动到其中。 用户可以移动的磁贴会突出显示。  
  
 `GridStripRenderer` 类自定义了 `GridStrip` 控件外观的三个方面：  
  
-   `GridStrip` 边框  
  
-   <xref:System.Windows.Forms.ToolStripButton> 边框  
  
-   <xref:System.Windows.Forms.ToolStripButton> 图像  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/CS/GridStrip.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.GridStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.GridStrip/VB/GridStrip.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。  另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.ToolStripRenderer>  
 <xref:System.Windows.Forms.ToolStripProfessionalRenderer>  
 <xref:System.Windows.Forms.ToolStripSystemRenderer>  
 <xref:System.Windows.Forms.StatusStrip>  
 [ToolStrip 控件](../../../../docs/framework/winforms/controls/toolstrip-control-windows-forms.md)
