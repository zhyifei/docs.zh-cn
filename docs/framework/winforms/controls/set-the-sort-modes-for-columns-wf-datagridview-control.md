---
title: 如何：设置 Windows 窗体 DataGridView 控件中列的排序模式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 08d90bb45006af798b629f58821cbf50ee9ef089
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535726"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a>如何：设置 Windows 窗体 DataGridView 控件中列的排序模式
在<xref:System.Windows.Forms.DataGridView>控件，文本框列使用自动排序默认情况下，而其他列类型不会自动排序。 有时想要覆盖这些默认值。 例如，可以显示图像以代替文本、 数字或枚举单元格的值。 映像不能进行排序，而它们表示的基础值可以进行排序。  
  
 在<xref:System.Windows.Forms.DataGridView>控件，<xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>的列的属性值确定其排序行为。  
  
 下面的过程演示`Priority`列从[如何： 在 Windows 窗体 DataGridView 控件中自定义数据格式](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。 此列是 image 列，不是默认情况下可排序。 它包含实际的单元值是字符串，但是，因此可以自动进行排序。  
  
### <a name="to-set-the-sort-mode-for-a-column"></a>若要设置列的排序模式  
  
-   设置 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> 属性。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件，其包含一个名为 `Priority` 的列。  
  
-   对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 [在 Windows 窗体 DataGridView 控件中进行数据排序](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的列排序模式](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中自定义排序](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
