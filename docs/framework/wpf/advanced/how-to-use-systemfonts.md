---
title: 如何：使用 SystemFonts
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
ms.openlocfilehash: 7438705a82faee464649b5f6f577627a379e9a8c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918361"
---
# <a name="how-to-use-systemfonts"></a>如何：使用 SystemFonts
此示例演示如何使用<xref:System.Windows.SystemFonts>类的静态资源来样式或自定义按钮。  
  
## <a name="example"></a>示例  
 系统资源将系统确定的许多值以资源和属性的形式公开，以帮助创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemFonts>是一个类, 其中包含作为静态属性的系统字体值和引用资源键的属性, 这些属性可用于在运行时动态访问这些值。 例如, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A>是一个<xref:System.Windows.SystemFonts>值, 并且<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>是对应的资源键。  
  
 在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中, 你可以使用的<xref:System.Windows.SystemFonts>成员作为静态属性或动态资源引用 (静态属性值作为键)。 如果希望字体规格在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态值引用。  
  
> [!NOTE]
> 资源键属性名称后面附有“Key”后缀。  
  
 下面的示例演示如何访问并将的<xref:System.Windows.SystemFonts>属性用作静态值, 以便样式或自定义按钮。 此标记示例为<xref:System.Windows.SystemFonts>按钮赋值。  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 若要在代码中<xref:System.Windows.SystemFonts>使用的值, 则不必使用静态值或动态资源引用。 请改用<xref:System.Windows.SystemFonts>类的非键属性。 尽管非键属性已明确定义为静态属性, 但是系统承载的的运行时行为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]将会实时重新评估这些属性, 并且将正确地考虑对系统值进行用户驱动的更改。 以下示例演示如何指定按钮的字体设置。  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.SystemFonts>
- [使用系统画笔绘制区域](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [使用 SystemParameters](how-to-use-systemparameters.md)
- [使用系统字体键](how-to-use-system-fonts-keys.md)
- [帮助主题](resources-how-to-topics.md)
- [x:Static 标记扩展](../../xaml-services/x-static-markup-extension.md)
- [XAML 资源](xaml-resources.md)
- [DynamicResource 标记扩展](dynamicresource-markup-extension.md)
