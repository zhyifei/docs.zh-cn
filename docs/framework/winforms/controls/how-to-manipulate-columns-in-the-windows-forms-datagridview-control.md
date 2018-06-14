---
title: 如何：操作 Windows 窗体 DataGridView 控件中的列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DataGridView control [Windows Forms], manipulatiing columns
- columns [Windows Forms], manipulating
- data grids [Windows Forms], manipulating columns
ms.assetid: d8cfe6b3-bbab-4182-bec2-0517d9f1eaf6
ms.openlocfilehash: e0becd4a60d4320f15c861c5bb004fb11d350bfe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532878"
---
# <a name="how-to-manipulate-columns-in-the-windows-forms-datagridview-control"></a>如何：操作 Windows 窗体 DataGridView 控件中的列
以下代码示例介绍了使用 <xref:System.Windows.Forms.DataGridViewColumn> 类的属性处理 <xref:System.Windows.Forms.DataGridView> 列的各种方法。  
  
## <a name="example"></a>示例  
 [!code-cpp[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CPP/DataGridViewColumnDemo.cpp#100)]
 [!code-csharp[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/CS/DataGridViewColumnDemo.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridView.ButtonDemos#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.ButtonDemos/VB/datagridviewcolumndemo.vb#100)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。  
  
 为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。  另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewBand>  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [使用 Windows 窗体 DataGridView 控件中的单元格、行和列编程](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
