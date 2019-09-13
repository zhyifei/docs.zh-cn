---
title: 如何：在 Windows 窗体中访问键控集合
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyed collections [Windows Forms]
- collections [Windows Forms], accessing with keys
ms.assetid: b9b79b8b-d9bf-4f8c-b9d6-9578bc3219d3
ms.openlocfilehash: a88e4766a1e774582bcd0356c9b6e77bc31f1960
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928526"
---
# <a name="how-to-access-keyed-collections-in-windows-forms"></a>如何：在 Windows 窗体中访问键控集合

- 可以通过键访问各个集合项。 此功能已添加到 Windows 窗体应用程序通常使用的许多集合类中。 下面的列表显示了一些具有可访问键控集合的集合类：  
  
- <xref:System.Windows.Forms.ListView.ListViewItemCollection>  
  
- <xref:System.Windows.Forms.ListViewItem.ListViewSubItemCollection>  
  
- <xref:System.Windows.Forms.Control.ControlCollection>  
  
- <xref:System.Windows.Forms.TabControl.TabPageCollection>  
  
- <xref:System.Windows.Forms.TreeNodeCollection>  
  
 与集合中的项关联的键通常是项的名称。 下面的过程演示如何使用集合类来执行常见任务。  
  
### <a name="to-find-and-give-focus-to-a-nested-control-in-a-control-collection"></a>查找焦点并将焦点放在控件集合中的嵌套控件上  
  
- <xref:System.Windows.Forms.Control.ControlCollection.Find%2A>使用和<xref:System.Windows.Forms.Control.Focus%2A>方法来指定要查找并将焦点提供给的控件的名称。  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#1)]  
  
### <a name="to-access-an-image-in-an-image-collection"></a>访问映像集合中的图像  
  
- 使用 " <xref:System.Windows.Forms.ImageList.ImageCollection.Item%2A>属性" 指定要访问的映像的名称。  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#2)]  
  
### <a name="to-set-a-tab-page-as-the-selected-tab"></a>将选项卡页设置为选定的选项卡  
  
- 结合使用<xref:System.Windows.Forms.TabControl.TabPageCollection.Item%2A>属性和属性以指定要设置为所选选项卡的选项卡页的名称。 <xref:System.Windows.Forms.TabControl.SelectedTab%2A>  
  
     [!code-csharp[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.KeyedCollectionsEx#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.KeyedCollectionsEx/VB/Form1.vb#3)]  
  
## <a name="see-also"></a>请参阅

- [Windows 窗体入门](getting-started-with-windows-forms.md)
- [如何：在 Windows 窗体 ImageList 组件中添加或删除图像](./controls/how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md)
