---
title: "如何：使用 Windows 窗体 ListView 控件在列中显示子项"
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
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be1b055c8ea0e7a7c6466033735431a17ecc32f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>如何：使用 Windows 窗体 ListView 控件在列中显示子项
Windows 窗体<xref:System.Windows.Forms.ListView>控件可以显示的附加文本或子项的详细信息视图中每个项。 第一列显示项文本，如雇员编号。 第二、 第三个和后续列显示第一、 第二，并随后的关联子项。  
  
### <a name="to-add-subitems-to-a-list-item"></a>要添加到列表项的子项  
  
1.  添加所需的任何列。 因为第一列将显示项的<xref:System.Windows.Forms.ListView.Text%2A>属性，你需要一列不是有子项。 添加列的详细信息，请参阅[如何： 向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)。  
  
2.  调用<xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A>方法返回的集合<xref:System.Windows.Forms.ListViewItem.SubItems%2A>项属性。 下面的代码示例设置的雇员姓名和部门的列表项。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>另请参阅  
 [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [如何：使用 Windows 窗体 ListView 控件添加和删除项](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [如何：向 Windows 窗体 ListView 控件添加列](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [如何：显示 Windows 窗体 ListView 控件的图标](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
