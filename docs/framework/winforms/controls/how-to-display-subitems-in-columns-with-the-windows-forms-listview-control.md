---
title: 用 ListView 控件在列中显示子项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- list items
- Details view
- ListView control [Windows Forms], adding ListSubItems
- subitems
ms.assetid: e465f044-cde7-4fd9-a687-788a73a0f554
ms.openlocfilehash: 5c6d807410ad4ee0198d6334844bd65b148edff4
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745541"
---
# <a name="how-to-display-subitems-in-columns-with-the-windows-forms-listview-control"></a>如何：使用 Windows 窗体 ListView 控件在列中显示子项
Windows 窗体 <xref:System.Windows.Forms.ListView> 控件可以为详细信息视图中的每个项显示其他文本或子项。 第一列显示项文本，例如雇员编号。 第二个、第三个和后续列显示第一个、第二个和后续关联的子项。  
  
### <a name="to-add-subitems-to-a-list-item"></a>将子项添加到列表项  
  
1. 添加所需的任何列。 因为第一列将显示项的 <xref:System.Windows.Forms.ListView.Text%2A> 属性，所以需要比子项更多的列。 有关添加列的详细信息，请参阅[如何：将列添加到 Windows 窗体 ListView 控件](how-to-add-columns-to-the-windows-forms-listview-control.md)。  
  
2. 调用由项的 <xref:System.Windows.Forms.ListViewItem.SubItems%2A> 属性返回的集合的 <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection.Add%2A> 方法。 下面的代码示例设置了一个列表项的雇员姓名和部门。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#61)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#61)]  
  
## <a name="see-also"></a>另请参阅

- [ListView 控件概述](listview-control-overview-windows-forms.md)
- [如何：使用 Windows 窗体 ListView 控件添加和删除项](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [如何：向 Windows 窗体 ListView 控件添加列](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [如何：显示 Windows 窗体 ListView 控件的图标](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息](add-custom-information-to-a-treeview-or-listview-control-wf.md)
