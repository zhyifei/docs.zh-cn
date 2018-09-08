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
ms.openlocfilehash: b972da093fc50563c5db93e61aeb8421f9bf20b2
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44087636"
---
# <a name="how-to-filter-data-in-a-view"></a>如何：筛选视图中的数据
此示例演示如何在视图中的数据进行筛选。  
  
## <a name="example"></a>示例  
 若要创建筛选器，定义的方法，提供筛选逻辑。 该方法用作回调并接受类型参数的`object`。 以下方法将返回所有`Order`对象与`filled`属性设置为"否"，筛选出的对象的其余部分。  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 然后可以应用筛选器，如下面的示例中所示。 在此示例中，`myCollectionView`是<xref:System.Windows.Data.ListCollectionView>对象。  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 若要撤销筛选，可以设置<xref:System.Windows.Data.CollectionView.Filter%2A>属性设置为`null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 有关如何创建或获取视图的信息，请参阅[获取数据集合的默认视图](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md)。 有关完整示例，请参阅[进行排序和筛选视图示例中的项目](https://go.microsoft.com/fwlink/?LinkID=160040)。  
  
 如果您的视图对象来自<xref:System.Windows.Data.CollectionViewSource>对象，你的设置的事件处理程序来应用筛选逻辑<xref:System.Windows.Data.CollectionViewSource.Filter>事件。 在以下示例中，`listingDataView`的一个实例<xref:System.Windows.Data.CollectionViewSource>。  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 下面显示了示例的实现`ShowOnlyBargainsFilter`筛选器事件处理程序。 此事件处理程序使用<xref:System.Windows.Data.FilterEventArgs.Accepted%2A>属性来筛选出`AuctionItem`具有对象`CurrentPrice`25 美元或更高版本。  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>  
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [在视图中对数据进行排序](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
