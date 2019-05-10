---
title: 如何：将对象绑定到 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: e1fef71de799f9f906c956a0441c92e027173a1c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64612348"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a>如何：将对象绑定到 Windows 窗体 DataGridView 控件
下面的代码示例演示如何将对象集合绑定到 <xref:System.Windows.Forms.DataGridView> 控件，以便每个对象可显示为单独的一行。 此示例还演示了如何显示 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 中具有枚举类型的属性，从而使组合框下拉列表包含枚举值。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 System 和 System.Windows.Forms 程序集的引用。  
  
 Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。 也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- [在 Windows 窗体 DataGridView 控件中显示数据](displaying-data-in-the-windows-forms-datagridview-control.md)
- [如何：访问对象绑定到 Windows 窗体 DataGridView 行](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
