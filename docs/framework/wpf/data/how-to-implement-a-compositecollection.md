---
title: 如何：实现 CompositeCollection
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
ms.openlocfilehash: 8361c2bfa9c125aeadf0a62ca86af1855e5c3dbc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931667"
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="96804-102">如何：实现 CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="96804-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="96804-103">示例</span><span class="sxs-lookup"><span data-stu-id="96804-103">Example</span></span>  
 <span data-ttu-id="96804-104">下面的示例演示如何使用 <xref:System.Windows.Data.CompositeCollection> 类将多个集合和项显示为一个列表。</span><span class="sxs-lookup"><span data-stu-id="96804-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="96804-105">在此示例中，`GreekGods` 是 `GreekGod` 自定义对象的一个 <xref:System.Collections.ObjectModel.ObservableCollection%601>。</span><span class="sxs-lookup"><span data-stu-id="96804-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="96804-106">定义了数据模板以便 `GreekGod` 对象和 `GreekHero` 对象分别以金色和青色作为前景色显示。</span><span class="sxs-lookup"><span data-stu-id="96804-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="96804-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="96804-107">See also</span></span>

- <xref:System.Windows.Data.CollectionContainer>
- <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>
- <xref:System.Windows.Data.XmlDataProvider>
- <xref:System.Windows.DataTemplate>
- [<span data-ttu-id="96804-108">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="96804-108">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="96804-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="96804-109">How-to Topics</span></span>](data-binding-how-to-topics.md)
