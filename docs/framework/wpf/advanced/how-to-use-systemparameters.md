---
title: "如何：使用 SystemParameters"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ec333fbc30374ff6f8e2e7674ab332644ff7aad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemparameters"></a>如何：使用 SystemParameters
此示例演示如何访问和使用的属性<xref:System.Windows.SystemParameters>才能样式或自定义按钮。  
  
## <a name="example"></a>示例  
 系统资源将多个基于系统的设置以资源的形式公开，以帮助创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemParameters>是一个类，包含系统参数值属性，并将绑定到值的资源键。 例如，<xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A>是<xref:System.Windows.SystemParameters>属性值和<xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>是相应的资源键。  
  
 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你可以使用的成员<xref:System.Windows.SystemParameters>为静态属性用法或 （具有作为键的静态属性值） 的动态资源引用。 如果希望基于系统的值在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态引用。 资源键具有后缀`Key`追加到属性名称。  
  
 下面的示例演示如何访问和使用的静态值<xref:System.Windows.SystemParameters>来设计或自定义按钮。 此标记示例通过应用大小按钮<xref:System.Windows.SystemParameters>至一个按钮的值。  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 若要使用的值<xref:System.Windows.SystemParameters>在代码中，你无需使用的静态引用或动态资源引用。 相反，使用的值<xref:System.Windows.SystemParameters>类。 虽然非键属性已明确定义为静态属性的运行时行为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]承载的系统将实时重新计算属性，并将正确的系统值对面向用户的更改的帐户。 下面的示例演示如何通过使用设置的宽度和按钮的高度<xref:System.Windows.SystemParameters>值。  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.SystemParameters>  
 [使用系统画笔绘制区域](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [使用 SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [使用系统参数键](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [帮助主题](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
