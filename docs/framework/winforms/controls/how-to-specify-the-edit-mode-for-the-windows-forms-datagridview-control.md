---
title: "如何：指定 Windows 窗体 DataGridView 控件的编辑模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], edit mode
- data grids [Windows Forms], edit mode
ms.assetid: 93e117e8-94c4-411b-ba31-645e475ed85c
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 70bf241865eef3366444e1b4dc20c19adaff983e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-edit-mode-for-the-windows-forms-datagridview-control"></a>如何：指定 Windows 窗体 DataGridView 控件的编辑模式
默认情况下，用户可以编辑的当前内容<xref:System.Windows.Forms.DataGridView>文本框单元格中通过键入它，或按 f2 键。 这将单元格置于编辑模式为如果满足所有以下条件：  
  
-   基础数据源支持编辑。  
  
-   <xref:System.Windows.Forms.DataGridView>启用控制。  
  
-   <xref:System.Windows.Forms.DataGridView.EditMode%2A>属性值不是<xref:System.Windows.Forms.DataGridViewEditMode.EditProgrammatically>。  
  
-   `ReadOnly`的单元格、 行、 列和控件的属性都设置为`false`。  
  
 在编辑模式下，用户可以更改单元格的值，然后按 enter 键以提交更改或按 ESC 键还原到其原始值的单元格。  
  
 你可以配置<xref:System.Windows.Forms.DataGridView>控制，以便在单元格进入编辑模式，只要它成为当前的单元格。 ENTER 和 ESC 键的行为是在这种情况下，不变，但此单元格处于编辑模式后的值是提交或还原。 以便单元格进入编辑模式，仅在单元格或仅当用户按 F2 用户键入时，还可以配置控件。 最后，可以防止单元格进入编辑模式，除非当调用<xref:System.Windows.Forms.DataGridView.BeginEdit%2A>方法。  
  
### <a name="to-change-the-edit-mode-of-a-datagridview-control"></a>更改 DataGridView 控件的编辑模式  
  
-   设置<xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>到适当的属性<xref:System.Windows.Forms.DataGridViewEditMode>枚举。  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#067)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#067](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#067)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
-   对 <xref:System> 和 <xref:System.Windows.Forms> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.EditMode%2A?displayProperty=nameWithType>  
 [Windows 窗体 DataGridView 控件中的数据输入](../../../../docs/framework/winforms/controls/data-entry-in-the-windows-forms-datagridview-control.md)
