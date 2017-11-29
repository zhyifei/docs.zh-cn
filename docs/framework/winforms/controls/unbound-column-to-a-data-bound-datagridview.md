---
title: "如何：将未绑定的列添加到绑定了数据的 Windows 窗体 DataGridView 控件"
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
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cd6a1494a98d912469f7e45c7751a0a9741ff17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>如何：将未绑定的列添加到绑定了数据的 Windows 窗体 DataGridView 控件
在 <xref:System.Windows.Forms.DataGridView> 控件中显示的数据通常来自某种类型的数据源，但你可能需要显示并非来自该数据源的一列数据。 这种列称为未绑定列。 未绑定列可有多种形式。 它们常用于提供对数据行详细信息的访问。  
  
 下面的代码示例演示如何创建的未绑定的列**详细信息**在实现主/从方案时，与父表中的特定行相关按钮以显示子表。 若要响应按钮点击，请实现显示包含子表的窗体的 <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType> 事件处理程序。  
  
 Visual Studio 中对此任务提供支持。  另请参阅[如何： 添加和删除 Windows 窗体 DataGridView 控件使用设计器中的列](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。  
  
-   对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Forms.DataGridView>  
 [在 Windows 窗体 DataGridView 控件中显示数据](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Windows 窗体 DataGridView 控件中的数据显示模式](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
