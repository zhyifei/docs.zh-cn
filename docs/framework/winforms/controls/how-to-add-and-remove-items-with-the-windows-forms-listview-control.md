---
title: 如何：添加和删除使用 Windows 窗体 ListView 控件的项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 7a4083d54ea85ff7a2e18f7e448f2b967317ac25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544518"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a>如何：添加和删除使用 Windows 窗体 ListView 控件的项
将项添加到 Windows 窗体的过程<xref:System.Windows.Forms.ListView>控件主要包括指定项并为其分配属性。 可在任何时间完成添加或删除列表项。  
  
### <a name="to-add-items-programmatically"></a>若要以编程方式添加项  
  
1.  使用<xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A>方法的<xref:System.Windows.Forms.ListView.Items%2A>属性。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a>若要以编程方式删除项目  
  
1.  使用<xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>或<xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>方法的<xref:System.Windows.Forms.ListView.Items%2A>属性。 <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A>方法中删除单个项;<xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A>方法从列表中移除所有项。  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Windows.Forms.ListView>
- [ListView 控件](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [ListView 控件概述](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
