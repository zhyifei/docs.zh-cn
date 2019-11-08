---
title: 如何：对分层数据使用主-从模式
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733480"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a>如何：对分层数据使用主-从模式
此示例演示如何实现主-从方案。  
  
## <a name="example"></a>示例  
 在此示例中，`LeagueList` 是 `Leagues`的集合。 每个 `League` 都有一个 `Name` 和一个 `Divisions`集合，每个 `Division` 都有一个名称和 `Teams`的集合。 每个 `Team` 都有一个团队名称。  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 下面是该示例的一个屏幕快照。 `Divisions` <xref:System.Windows.Controls.ListBox> 会自动跟踪 `Leagues` <xref:System.Windows.Controls.ListBox> 中的选定内容，并显示相应的数据。 `Teams` <xref:System.Windows.Controls.ListBox> 跟踪其他两个 <xref:System.Windows.Controls.ListBox> 控件中的选定内容。  
  
 ![显示主&#45;详细方案示例的屏幕截图。](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 在此示例中，需要注意以下两个事项：  
  
1. 这三个 <xref:System.Windows.Controls.ListBox> 控件绑定到同一个源。 可以设置绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性，以指定希望 <xref:System.Windows.Controls.ListBox> 显示哪一级别的数据。  
  
2. 必须在要跟踪的选定内容的 <xref:System.Windows.Controls.ListBox> 控件上将 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 属性设置为 `true`。 设置此属性可确保选定项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。 或者，如果 <xref:System.Windows.Controls.ListBox> 从 <xref:System.Windows.Data.CollectionViewSource>中获取数据，则会自动同步选定内容和货币。  
  
 使用 XML 数据时，技术略有不同。 有关示例，请参阅对[分层 XML 数据使用主-从模式](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.HierarchicalDataTemplate>
- [绑定到集合并根据选择的内容显示信息](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [数据模板化概述](data-templating-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
