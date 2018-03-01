---
title: "如何：处理 ListView 中每一项的 MouseDoubleClick 事件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3fef9655ab95328e027a303df57c3359a7676eac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>如何：处理 ListView 中每一项的 MouseDoubleClick 事件
若要处理的事件中的项<xref:System.Windows.Controls.ListView>，你需要将事件处理程序添加到每<xref:System.Windows.Controls.ListViewItem>。 当<xref:System.Windows.Controls.ListView>绑定到数据源，你无需显式创建<xref:System.Windows.Controls.ListViewItem>，但你可以通过添加处理每个项的事件<xref:System.Windows.EventSetter>为的样式<xref:System.Windows.Controls.ListViewItem>。  
  
## <a name="example"></a>示例  
 下面的示例创建数据绑定<xref:System.Windows.Controls.ListView>并创建<xref:System.Windows.Style>将事件处理程序添加到每个<xref:System.Windows.Controls.ListViewItem>。  
  
 [!code-xaml[ListViewHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 下面的示例处理<xref:System.Windows.Controls.Control.MouseDoubleClick>事件。  
  
 [!code-csharp[ListViewHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
>  尽管它是最常见绑定<xref:System.Windows.Controls.ListView>到数据源，可以使用一种样式，将事件处理程序添加到每个<xref:System.Windows.Controls.ListViewItem>中非-数据绑定<xref:System.Windows.Controls.ListView>无论是否显式创建<xref:System.Windows.Controls.ListViewItem>。  有关详细信息创建显式和隐式<xref:System.Windows.Controls.ListViewItem>控件，请参阅<xref:System.Windows.Controls.ItemsControl>。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.XmlElement>  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [使用 XMLDataProvider 和 XPath 查询绑定到 XML 数据](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)  
 [ListView 概述](../../../../docs/framework/wpf/controls/listview-overview.md)
