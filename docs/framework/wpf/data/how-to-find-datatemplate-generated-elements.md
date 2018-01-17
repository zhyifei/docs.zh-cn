---
title: "如何：查找由 DataTemplate 生成的元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- finding DataTemplate elements [WPF]
- DataTemplate [WPF]
ms.assetid: bfcd564e-5e9e-451e-8641-a9b5c3cfac90
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 481a22cfd9419d36473c77b5d2282a711259e031
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-datatemplate-generated-elements"></a>如何：查找由 DataTemplate 生成的元素
此示例演示如何查找元素所生成的<xref:System.Windows.DataTemplate>。  
  
## <a name="example"></a>示例  
 在此示例中，没有<xref:System.Windows.Controls.ListBox>，它绑定到某些[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]数据：  
  
 [!code-xaml[FindGeneratedItems#LB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#lb)]  
  
 <xref:System.Windows.Controls.ListBox>使用以下<xref:System.Windows.DataTemplate>:  
  
 [!code-xaml[FindGeneratedItems#DT](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml#dt)]  
  
 如果你想要检索<xref:System.Windows.Controls.TextBlock>元素生成的<xref:System.Windows.DataTemplate>的某一特定<xref:System.Windows.Controls.ListBoxItem>，您需要先获取<xref:System.Windows.Controls.ListBoxItem>，查找<xref:System.Windows.Controls.ContentPresenter>在其中<xref:System.Windows.Controls.ListBoxItem>，然后调用<xref:System.Windows.FrameworkTemplate.FindName%2A>上<xref:System.Windows.DataTemplate>它被设置上<xref:System.Windows.Controls.ContentPresenter>。 下面的示例演示如何执行这些步骤。 出于演示目的，此示例将创建一个消息框，显示的文本内容的<xref:System.Windows.DataTemplate>-生成的文本块。  
  
 [!code-csharp[FindGeneratedItems#DTFindElement](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#dtfindelement)]
 [!code-vb[FindGeneratedItems#DTFindElement](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#dtfindelement)]  
  
 以下是实现的`FindVisualChild`，它使用<xref:System.Windows.Media.VisualTreeHelper>方法：  
  
 [!code-csharp[FindGeneratedItems#FVC](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FindGeneratedItems/CSharp/Window1.xaml.cs#fvc)]
 [!code-vb[FindGeneratedItems#FVC](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FindGeneratedItems/VisualBasic/Window1.xaml.vb#fvc)]  
  
## <a name="see-also"></a>请参阅  
 [如何：查找由 ControlTemplate 生成的元素](../../../../docs/framework/wpf/controls/how-to-find-controltemplate-generated-elements.md)  
 [数据绑定概述](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [帮助主题](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)  
 [WPF XAML 名称范围](../../../../docs/framework/wpf/advanced/wpf-xaml-namescopes.md)  
 [WPF 中的树](../../../../docs/framework/wpf/advanced/trees-in-wpf.md)
