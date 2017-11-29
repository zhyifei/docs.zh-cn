---
title: "如何：对分层数据使用主-从模式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>如何：对分层数据使用主-从模式
此示例演示如何实现主 / 从方案。  
  
## <a name="example"></a>示例  
 在此示例中，`LeagueList`是一套`Leagues`。 每个`League`具有`Name`和一系列`Divisions`，和每个`Division`有一个名称和一套`Teams`。 每个`Team`有一个团队名称。  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 下面是该示例的一个屏幕快照。 `Divisions` <xref:System.Windows.Controls.ListBox>自动跟踪中的选择`Leagues`<xref:System.Windows.Controls.ListBox>并显示相应的数据。 `Teams` <xref:System.Windows.Controls.ListBox>跟踪中与其他两个选项<xref:System.Windows.Controls.ListBox>控件。  
  
 ![Master &#45; 详细信息示例](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")  
  
 需要注意，在此示例中，两个的事项为：  
  
1.  这三种<xref:System.Windows.Controls.ListBox>的控件绑定到相同的源。 你设置<xref:System.Windows.Data.Binding.Path%2A>要指定所需的数据级别的绑定属性<xref:System.Windows.Controls.ListBox>以显示。  
  
2.  必须设置<xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A>属性`true`上<xref:System.Windows.Controls.ListBox>种控件跟踪所做的选择。 将设置此属性可确保所选的项始终设置为<xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。 或者，如果<xref:System.Windows.Controls.ListBox>获取它从数据<xref:System.Windows.Data.CollectionViewSource>，它自动同步所选内容和货币。  
  
 这种方法是略有不同，当你使用[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据。 有关示例，请参阅[对层次结构的 XML 数据使用主-详细信息模式](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [绑定到集合并根据选择的内容显示信息](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [数据模板化概述](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [操作说明主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
