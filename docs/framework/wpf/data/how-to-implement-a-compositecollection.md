---
title: 如何：实现 CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 2021ed83a8f2a6896631fa69d5dd55a74cad8a8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54691861"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="63df2-102">如何：实现 CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="63df2-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="63df2-103">示例</span><span class="sxs-lookup"><span data-stu-id="63df2-103">Example</span></span>  
 <span data-ttu-id="63df2-104">下面的示例演示如何使用 <xref:System.Windows.Data.CompositeCollection> 类将多个集合和项显示为一个列表。</span><span class="sxs-lookup"><span data-stu-id="63df2-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="63df2-105">在此示例中，`GreekGods` 是 `GreekGod` 自定义对象的一个 <xref:System.Collections.ObjectModel.ObservableCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="63df2-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="63df2-106">定义了数据模板以便 `GreekGod` 对象和 `GreekHero` 对象分别以金色和青色作为前景色显示。</span><span class="sxs-lookup"><span data-stu-id="63df2-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="63df2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="63df2-107">See also</span></span>
- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="63df2-108">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="63df2-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="63df2-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="63df2-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
