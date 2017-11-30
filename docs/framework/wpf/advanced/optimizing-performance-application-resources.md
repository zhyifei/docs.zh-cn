---
title: "优化性能：应用程序资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ac462f3b49788fd909f9d9f4fc785db74704ff6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="optimizing-performance-application-resources"></a>优化性能：应用程序资源
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]允许你共享应用程序资源，以便你可以跨类似类型的元素支持一个一致的外观或行为。 本主题提供了一些建议在此区域中，可帮助你提高你的应用程序的性能。  
  
 有关资源的详细信息，请参阅 [XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
## <a name="sharing-resources"></a>共享资源  
 如果你的应用程序使用自定义控件，并定义中的资源<xref:System.Windows.ResourceDictionary>（或 XAML 资源节点），建议，你可以定义的资源在<xref:System.Windows.Application>或<xref:System.Windows.Window>对象级别，或定义它们中的默认主题自定义控件。 在一个自定义控件中定义资源<xref:System.Windows.ResourceDictionary>施加了该控件的每个实例的性能造成影响。 例如，如果你有性能要求较高画笔操作定义为资源定义的自定义控件的一部分和自定义控件的多个实例，则应用程序的工作集将显著增加。  
  
 为了说明这一点，请考虑以下。 假设你正在开发卡游戏 using [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]。 对于大多数纸牌游戏，你需要 52 卡，52 不同的外观。 你决定实现卡自定义控件和中的卡自定义控件的资源定义 （每个元素表示一种纸牌外观） 的 52 画笔。 在主应用程序，你最初创建此卡自定义控件的 52 的实例。 卡自定义控件的每个实例生成的 52 实例<xref:System.Windows.Media.Brush>对象，使您总共有的 52 * 52<xref:System.Windows.Media.Brush>你的应用程序中的对象。 通过移动到的卡自定义控件资源超出画笔<xref:System.Windows.Application>或<xref:System.Windows.Window>对象级别，或定义它们中的自定义控件的默认主题您降低应用程序的工作集，因为现在正在共享 52 画笔之间的卡控件的 52 实例。  
  
## <a name="sharing-a-brush-without-copying"></a>而不复制共享画笔  
 如果必须使用相同的多个元素<xref:System.Windows.Media.Brush>对象、 为资源定义画笔和引用它，而不定义画笔内联在[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]。 此方法将创建一个实例，并重复使用它，而定义画笔内联在[!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]创建的每个元素的新实例。  
  
 下面的标记示例说明了这一点：  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>使用静态资源尽可能  
 静态资源通过查找对已定义的资源的引用的任何 XAML 属性提供一个值。 该资源的查找行为是类似于编译时查找。  
  
 动态资源，另一方面，将创建一个临时在初始编译表达式，并因此的操作延迟的资源的查找请求的资源值是构造一个对象才能实际必需的。 该资源的查找行为是类似于运行时查找，它会影响性能。 使用尽可能使用动态资源仅在必要时对应用程序中的静态资源。  
  
 下面的标记示例演示如何使用两种类型的资源：  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>另请参阅  
 [优化 WPF 应用程序性能](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [规划应用程序性能](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [利用硬件](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [布局和示例](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [2D 图形和图像处理](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [对象行为](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [“文本”](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [数据绑定](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [其他性能建议](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
