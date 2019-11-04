---
title: 如何：筛选视图中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: ea49897ca5e9cb6b639cf7d98ff05bd287c51761
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73453481"
---
# <a name="how-to-filter-data-in-a-view"></a>如何：筛选视图中的数据
此示例演示如何在视图中筛选数据。  
  
## <a name="example"></a>示例  
 若要创建筛选器，请定义提供筛选逻辑的方法。 方法用作回调并接受类型 `object`的参数。 下面的方法将返回 `filled` 属性设置为 "No" 的所有 `Order` 对象，并筛选掉对象的其余部分。  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 然后，你可以应用筛选器，如以下示例中所示。 在此示例中，`myCollectionView` 是 <xref:System.Windows.Data.ListCollectionView> 对象。  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 若要撤消筛选，可以将 <xref:System.Windows.Data.CollectionView.Filter%2A> 属性设置为 `null`：  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 有关如何创建或获取视图的信息，请参阅[获取数据集合的默认视图](how-to-get-the-default-view-of-a-data-collection.md)。 有关完整示例，请参阅[在视图示例中对项目进行排序和筛选](https://go.microsoft.com/fwlink/?LinkID=160040)。  
  
 如果视图对象来自 <xref:System.Windows.Data.CollectionViewSource> 对象，则可以通过为 <xref:System.Windows.Data.CollectionViewSource.Filter> 事件设置事件处理程序来应用筛选逻辑。 在下面的示例中，`listingDataView` 是 <xref:System.Windows.Data.CollectionViewSource>的实例。  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 下面的示例演示如何实现 `ShowOnlyBargainsFilter` 筛选器事件处理程序。 此事件处理程序使用 <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> 属性筛选出 `CurrentPrice` 为 $25 或更高的 `AuctionItem` 对象。  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [数据绑定概述](../../../desktop-wpf/data/data-binding-overview.md)
- [在视图中对数据进行排序](how-to-sort-data-in-a-view.md)
- [帮助主题](data-binding-how-to-topics.md)
