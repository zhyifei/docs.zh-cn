---
title: 选择 ListView 控件中的项
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743228"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a>如何：选择 Windows 窗体 ListView 控件中的项
此示例演示如何以编程方式选择 Windows 窗体 <xref:System.Windows.Forms.ListView> 控件中的项。 以编程方式选择项并不会自动将焦点更改为 <xref:System.Windows.Forms.ListView> 控件。 出于此原因，在选择项时，通常还需要将项设置为聚焦项。  
  
## <a name="example"></a>示例  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 一个名为 `listView1` 的 <xref:System.Windows.Forms.ListView> 控件，其中至少包含一项。  
  
- 对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
