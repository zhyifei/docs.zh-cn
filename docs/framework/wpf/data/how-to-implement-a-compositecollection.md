---
title: 如何：实现 CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: f8af8d806b8c889be11533392ee3c831399e9ab7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556112"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="2d8cd-102">如何：实现 CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="2d8cd-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="2d8cd-103">示例</span><span class="sxs-lookup"><span data-stu-id="2d8cd-103">Example</span></span>  
 <span data-ttu-id="2d8cd-104">下面的示例演示如何使用 <xref:System.Windows.Data.CompositeCollection> 类将多个集合和项显示为一个列表。</span><span class="sxs-lookup"><span data-stu-id="2d8cd-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="2d8cd-105">在此示例中，`GreekGods` 是 `GreekGod` 自定义对象的一个 <xref:System.Collections.ObjectModel.ObservableCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="2d8cd-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="2d8cd-106">定义了数据模板以便 `GreekGod` 对象和 `GreekHero` 对象分别以金色和青色作为前景色显示。</span><span class="sxs-lookup"><span data-stu-id="2d8cd-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2d8cd-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d8cd-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="2d8cd-108">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="2d8cd-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="2d8cd-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="2d8cd-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
