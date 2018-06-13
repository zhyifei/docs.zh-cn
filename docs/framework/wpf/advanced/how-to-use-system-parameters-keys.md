---
title: 如何：使用系统参数键
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: c94719c8268cbbdadbe6805d531540e1f34ee5d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544711"
---
# <a name="how-to-use-system-parameters-keys"></a>如何：使用系统参数键
系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemParameters> 是一个类，包含系统参数值和绑定到这些值的资源键 — 例如，<xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A>和<xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>。 系统参数规格可用作静态或动态资源。 如果希望参数规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。  
  
> [!NOTE]
>  动态资源具有关键字*密钥*追加到属性名称。  
  
 以下示例演示如何访问和使用系统参数动态资源来设计按钮样式或自定义按钮。 这[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例调整按钮通过分配的大小<xref:System.Windows.SystemParameters>值与按钮的宽度和高度。  
  
## <a name="example"></a>示例  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>请参阅  
 [使用系统画笔绘制区域](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [使用 SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [使用 SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
