---
title: "如何：使用 CheckBox 创建 ListViewItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4cc6ebb3671dcc65d690fde5d4796c9034553eb7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>如何：使用 CheckBox 创建 ListViewItem
此示例演示如何显示一列的<xref:System.Windows.Controls.CheckBox>中控制<xref:System.Windows.Controls.ListView>使用控件<xref:System.Windows.Controls.GridView>。  
  
## <a name="example"></a>示例  
 若要创建一列以包含<xref:System.Windows.Controls.CheckBox>中控制<xref:System.Windows.Controls.ListView>，创建<xref:System.Windows.DataTemplate>包含<xref:System.Windows.Controls.CheckBox>。 然后设置<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>的<xref:System.Windows.Controls.GridViewColumn>到<xref:System.Windows.DataTemplate>。  
  
 下面的示例演示<xref:System.Windows.DataTemplate>包含<xref:System.Windows.Controls.CheckBox>。 该示例将绑定<xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A>属性<xref:System.Windows.Controls.CheckBox>到<xref:System.Windows.Controls.ListBoxItem.IsSelected%2A>属性值<xref:System.Windows.Controls.ListViewItem>包含它。 因此，当<xref:System.Windows.Controls.ListViewItem>包含<xref:System.Windows.Controls.CheckBox>选中，则<xref:System.Windows.Controls.CheckBox>已选中。  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 下面的示例演示如何创建一列<xref:System.Windows.Controls.CheckBox>控件。 若要将列，该示例设置<xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A>属性<xref:System.Windows.Controls.GridViewColumn>到<xref:System.Windows.DataTemplate>。  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.Controls.Control>  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [GridView 概述](../../../../docs/framework/wpf/controls/gridview-overview.md)
