---
title: "如何：使数据可用于 XAML 中的绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], making data available for binding
- binding data [WPF], making data available for
ms.assetid: 7103c2e8-0e31-4a13-bf12-ca382221a8d5
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0c342f0d635a9220a88a2af79c76e2c1580dee2f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-make-data-available-for-binding-in-xaml"></a>如何：使数据可用于 XAML 中的绑定
本主题讨论您可以使数据可用于在绑定的不同方式[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，取决于你的应用程序的需求。  
  
## <a name="example"></a>示例  
 如果你有[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象你想要将绑定到中[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你可以使该对象可绑定是定义为资源并为其提供的一种方法`x:Key`。 在下面的示例中，你有`Person`具有名为的字符串属性对象`PersonName`。 `Person`对象在调用的命名空间中定义`SDKSample`。  
  
 [!code-xaml[SimpleBinding#Instantiation](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#instantiation)]  
[!code-xaml[SimpleBinding#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#2)]  
  
 你可以随后可以绑定到中的对象[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，下面的示例中所示。  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 或者，可以使用<xref:System.Windows.Data.ObjectDataProvider>类，如以下示例所示。  
  
 [!code-xaml[SimpleBinding#ODPCP](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Page1.xaml#odpcp)]  
  
 定义绑定相同的方式：  
  
 [!code-xaml[SimpleBinding#BDO1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml#bdo1)]  
  
 在此特定示例中，结果是相同的： 必须<xref:System.Windows.Controls.TextBlock>的文本内容与`Joe`。 但是，<xref:System.Windows.Data.ObjectDataProvider>类提供如能够绑定到方法的结果的功能。 你可以选择使用<xref:System.Windows.Data.ObjectDataProvider>类如果你需要它提供的功能。  
  
 但是，如果你正在绑定到已创建的对象，你需要设置`DataContext`在代码中，如以下示例所示。  
  
 [!code-csharp[ADODataSet#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ADODataSet/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ADODataSet#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ADODataSet/VisualBasic/Window1.xaml.vb#1)]  
  
 访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]绑定使用的数据<xref:System.Windows.Data.XmlDataProvider>类，请参阅[将绑定到 XML 数据使用 XPath 查询和 XMLDataProvider](../../../../docs/framework/wpf/data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)。 访问[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]绑定使用的数据<xref:System.Windows.Data.ObjectDataProvider>类，请参阅[XML 查询结果绑定到 XDocument、 XElement 或 LINQ](../../../../docs/framework/wpf/data/how-to-bind-to-xdocument-xelement-or-linq-for-xml-query-results.md)。  
  
 你可以指定要绑定到的数据的不同方法的信息，请参阅[指定绑定源](../../../../docs/framework/wpf/data/how-to-specify-the-binding-source.md)。 有关可以绑定到哪些类型的数据或实现你自己的方式信息[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]对象的绑定，请参阅[绑定源概述](../../../../docs/framework/wpf/data/binding-sources-overview.md)。  
  
## <a name="see-also"></a>请参阅  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
