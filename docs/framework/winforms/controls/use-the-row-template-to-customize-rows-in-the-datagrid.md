---
title: 如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966496"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>如何：使用行模板自定义 Windows 窗体 DataGridView 控件中的行
控件将行模板用作通过数据绑定或在<xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType>调用方法时未指定要使用的现有行的所有行的基础。 <xref:System.Windows.Forms.DataGridView>  
  
 行模板使你可以更好地控制行的外观和行为, 而<xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>不是属性提供的。 利用行模板, 可以设置任何<xref:System.Windows.Forms.DataGridViewRow>属性, 包括。 <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>  
  
 在某些情况下, 您必须使用行模板来实现特定的效果。 例如, 行高信息无法存储在中<xref:System.Windows.Forms.DataGridViewCellStyle>, 因此您必须使用行模板来更改所有行使用的默认高度。 当您创建自己的<xref:System.Windows.Forms.DataGridViewRow>派生自的类, 并且您希望在将新行添加到控件时使用您的自定义类型时, 行模板也很有用。  
  
> [!NOTE]
> 行模板仅在添加行时使用。 不能通过更改行模板来更改现有行。  
  
### <a name="to-use-the-row-template"></a>使用行模板  
  
- 设置从<xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>属性中检索的对象的属性。  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
- 对 <xref:System?displayProperty=nameWithType><xref:System.Drawing?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Windows 窗体 DataGridView 控件中的基本格式和样式设置](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Windows 窗体 DataGridView 控件中的单元格样式](cell-styles-in-the-windows-forms-datagridview-control.md)
