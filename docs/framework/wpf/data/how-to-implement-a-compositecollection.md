---
title: "如何：实现 CompositeCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: data binding [WPF], CompositeCollection class
ms.assetid: 0d8fc84c-7920-427f-8ad7-d55ca656c170
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d7d9610c6c507ebdebdb5690dcb7aec19599ee80
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-implement-a-compositecollection"></a><span data-ttu-id="c9b42-102">如何：实现 CompositeCollection</span><span class="sxs-lookup"><span data-stu-id="c9b42-102">How to: Implement a CompositeCollection</span></span>
## <a name="example"></a><span data-ttu-id="c9b42-103">示例</span><span class="sxs-lookup"><span data-stu-id="c9b42-103">Example</span></span>  
 <span data-ttu-id="c9b42-104">下面的示例演示如何将多个集合和项显示为一个列表使用<xref:System.Windows.Data.CompositeCollection>类。</span><span class="sxs-lookup"><span data-stu-id="c9b42-104">The following example shows how to display multiple collections and items as one list using the <xref:System.Windows.Data.CompositeCollection> class.</span></span> <span data-ttu-id="c9b42-105">在此示例中，`GreekGods`是<xref:System.Collections.ObjectModel.ObservableCollection%601>的`GreekGod`自定义对象。</span><span class="sxs-lookup"><span data-stu-id="c9b42-105">In this example, `GreekGods` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `GreekGod` custom objects.</span></span> <span data-ttu-id="c9b42-106">定义数据模板，以便`GreekGod`对象和`GreekHero`对象为金色和青色前景颜色分别显示。</span><span class="sxs-lookup"><span data-stu-id="c9b42-106">Data templates are defined so that `GreekGod` objects and `GreekHero` objects appear with a gold and a cyan foreground color respectively.</span></span>  
  
 [!code-xaml[CompositeCollections#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CompositeCollections/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c9b42-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9b42-107">See Also</span></span>  
 <xref:System.Windows.Data.CollectionContainer>  
 <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>  
 <xref:System.Windows.Data.XmlDataProvider>  
 <xref:System.Windows.DataTemplate>  
 [<span data-ttu-id="c9b42-108">数据绑定概述</span><span class="sxs-lookup"><span data-stu-id="c9b42-108">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="c9b42-109">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="c9b42-109">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
