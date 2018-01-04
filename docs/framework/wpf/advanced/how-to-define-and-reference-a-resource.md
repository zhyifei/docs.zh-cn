---
title: "如何：定义和引用资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 173be3048f7bf082db2eef2ea21eb1e0319f9a43
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-define-and-reference-a-resource"></a>如何：定义和引用资源
此示例演示如何定义资源，通过使用中的属性引用该[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]。  
  
## <a name="example"></a>示例  
 下面的示例定义两种类型的资源：<xref:System.Windows.Media.SolidColorBrush>资源，并在几个<xref:System.Windows.Style>资源。 <xref:System.Windows.Media.SolidColorBrush>资源`MyBrush`用来提供多个属性的值在每个都采用<xref:System.Windows.Media.Brush>键入值。 <xref:System.Windows.Style>资源`PageBackground`，`TitleText`和`Label`每面向特定控件类型。 样式目标控件上设置多个不同的属性，该样式资源由资源键引用，以及用于设置<xref:System.Windows.FrameworkElement.Style%2A>属性中定义的几个特定的控件元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]。  
  
 第一个属性的 setter 中注意`Label`样式也引用`MyBrush`前面定义的资源。 这是一种常用技术，但务必记住，资源是分析，并输入到的资源字典中，系统会提供的顺序。 如果你使用在字典中找到的顺序也所请求资源[否则标记扩展](../../../../docs/framework/wpf/advanced/staticresource-markup-extension.md)引用它们从另一个资源中。 请确保你引用任何资源比然后请求该资源时资源集合中之前定义。 如果有必要，你可以解决资源这样的严格的创建顺序使用[DynamicResource 标记扩展](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)可以引用在运行时该资源，相反，但你应注意，此 DynamicResource技术对性能产生影响。 有关详细信息，请参阅[XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)。  
  
 [!code-xaml[FEResource#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]  
  
## <a name="see-also"></a>请参阅  
 [XAML 资源](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [样式设置和模板化](../../../../docs/framework/wpf/controls/styling-and-templating.md)
