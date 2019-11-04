---
title: 如何：绑定到集合并基于选择显示信息
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459147"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a>如何：绑定到集合并基于选择显示信息
在简单的主-从方案中，有一个数据绑定 <xref:System.Windows.Controls.ItemsControl>，如 <xref:System.Windows.Controls.ListBox>。 根据用户选择，将显示有关所选项目的详细信息。 此示例演示如何实现此方案。  
  
## <a name="example"></a>示例  
 在此示例中，`People` 是 `Person` 类的 <xref:System.Collections.ObjectModel.ObservableCollection%601>。 此 `Person` 类包含三个属性： `FirstName`、`LastName`和 `HomeTown`，所有类型 `string`。  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <xref:System.Windows.Controls.ContentControl> 使用以下 <xref:System.Windows.DataTemplate> 来定义 `Person` 信息的显示方式：  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 下面是此示例生成内容的屏幕截图。 <xref:System.Windows.Controls.ContentControl> 显示所选人员的其他属性。  
  
 ![绑定到集合](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")  
  
 在此示例中，需要注意以下两个事项：  
  
1. <xref:System.Windows.Controls.ListBox> 和 <xref:System.Windows.Controls.ContentControl> 绑定到同一个源。 未指定这两个绑定的 <xref:System.Windows.Data.Binding.Path%2A> 属性，因为这两个控件都绑定到整个集合对象。  
  
2. 必须将 <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> 属性设置为 `true` 才能使此操作生效。 设置此属性可确保选定项始终设置为 <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>。 或者，如果 <xref:System.Windows.Controls.ListBox> 从 <xref:System.Windows.Data.CollectionViewSource>中获取数据，则会自动同步选定内容和货币。  
  
 请注意，`Person` 类按以下方式重写 `ToString` 方法。 默认情况下，<xref:System.Windows.Controls.ListBox> 调用 `ToString` 并显示绑定集合中每个对象的字符串表示形式。 这就是每个 `Person` 在 <xref:System.Windows.Controls.ListBox>中出现的名字的原因。  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a>请参阅

- [将主-详细模式与分层数据结合使用](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [将主-详细模式与分层 XML 数据结合使用](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [数据模板化概述](data-templating-overview.md)
- [帮助主题](data-binding-how-to-topics.md)
