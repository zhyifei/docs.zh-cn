---
title: "如何：实现 CompositeCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b33e3a61b91c2f9e2362a270216038d61770b815
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="22666-102">如何：实现 CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="22666-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="22666-103">示例</span><span class="sxs-lookup"><span data-stu-id="22666-103">Example</span></span>  
 <span data-ttu-id="22666-104">下面的示例演示如何将多个集合和项显示为一个列表使用<xref:System.Windows.Data.CompositeCollection>类。</span><span class="sxs-lookup"><span data-stu-id="22666-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="22666-105">在此示例中，`GreekGods`是<xref:System.Collections.ObjectModel.ObservableCollection%601>的`GreekGod`自定义对象。</span><span class="sxs-lookup"><span data-stu-id="22666-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="22666-106">定义数据模板，以便`GreekGod`对象和`GreekHero`对象为金色和青色前景颜色分别显示。</span><span class="sxs-lookup"><span data-stu-id="22666-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="22666-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="22666-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="22666-108">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="22666-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="22666-109">帮助主题</span><span class="sxs-lookup"><span data-stu-id="22666-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
