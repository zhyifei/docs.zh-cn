---
title: 如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cells [Windows Forms], displaying images
- data grids [Windows Forms], displaying in grids
- DataGridView control [Windows Forms], displaying images
- data grids [Windows Forms], displaying images in cells
ms.assetid: 53b13d31-1b56-476d-9ab4-18bfac138a22
ms.openlocfilehash: 62a29b9ade4953a1775c2a71b62e4881065f51a6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33531188"
---
# <a name="how-to-display-images-in-cells-of-the-windows-forms-datagridview-control"></a>如何：在 Windows 窗体 DataGridView 控件的单元格中显示图像
图片或图形是你可以在数据行中显示的值之一。 通常情况下，这些图形需要员工的照片或公司徽标的形式。  
  
 显示中的数据时，并入图片很简单<xref:System.Windows.Forms.DataGridView>控件。 <xref:System.Windows.Forms.DataGridView>控件本身处理支持的任何图像格式<xref:System.Drawing.Image>类，以及 OLE 图某些数据库使用的格式。  
  
 如果<xref:System.Windows.Forms.DataGridView>控件的数据源具有一列图像，它们将自动显示<xref:System.Windows.Forms.DataGridView>控件。  
  
 下面的代码示例演示如何从嵌入的资源提取图标并将其转换为 image 列的每个单元中显示的位图。 文本的单元格的值替换为相应的图像的另一个示例，请参阅[如何： 在 Windows 窗体 DataGridView 控件中自定义数据格式](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#050)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#050](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#050)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
-   名为嵌入的图标资源`tree.ico`。  
  
-   对 <xref:System?displayProperty=nameWithType><xref:System.Windows.Forms?displayProperty=nameWithType> 和 <xref:System.Drawing?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [Windows 窗体 DataGridView 控件中的列、行和单元格基本功能](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [如何：在 Windows 窗体 DataGridView 控件中自定义数据格式设置](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md)
