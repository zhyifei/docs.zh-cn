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
ms.openlocfilehash: 157565ceb9057049aef8b2bf274847d58c6b8dc8
ms.sourcegitcommit: f8c36054eab877de4d40a705aacafa2552ce70e9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/31/2019
ms.locfileid: "75559958"
---
# <a name="how-to-use-systemfonts"></a>如何：使用 SystemFonts
此示例演示如何使用 <xref:System.Windows.SystemFonts> 类的静态资源来样式或自定义按钮。  
  
## <a name="example"></a>示例  
 系统资源将系统确定的许多值以资源和属性的形式公开，以帮助创建与系统设置一致的视觉效果。 <xref:System.Windows.SystemFonts> 是一种类，其中包含作为静态属性的系统字体值和引用资源键的属性，这些属性可用于在运行时动态访问这些值。 例如，<xref:System.Windows.SystemFonts.CaptionFontFamily%2A> 是 <xref:System.Windows.SystemFonts> 值，<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> 是相应的资源键。  
  
 在 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]中，可以使用 <xref:System.Windows.SystemFonts> 的成员作为静态属性或动态资源引用（静态属性值作为键）。 如果希望字体规格在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态值引用。  
  
> [!NOTE]
> 资源键属性名称后面附有“Key”后缀。  
  
 下面的示例演示了如何访问和使用 <xref:System.Windows.SystemFonts> 的属性作为静态值，以便样式或自定义按钮。 此标记示例将 <xref:System.Windows.SystemFonts> 值分配给某个按钮。  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 若要在代码中使用 <xref:System.Windows.SystemFonts> 的值，则不必使用静态值或动态资源引用。 请改用 <xref:System.Windows.SystemFonts> 类的非键属性。 尽管非键属性已明确定义为静态属性，但是系统承载的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 的运行时行为将会实时重新评估这些属性，并且将正确地考虑对系统值进行用户驱动的更改。 以下示例演示如何指定按钮的字体设置。  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.SystemFonts>
- [使用系统画笔绘制区域](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [使用 SystemParameters](how-to-use-systemparameters.md)
- [使用系统字体键](how-to-use-system-fonts-keys.md)
- [帮助主题](resources-how-to-topics.md)
- [x:Static 标记扩展](../../../desktop-wpf/xaml-services/xstatic-markup-extension.md)
- [XAML 资源](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [DynamicResource 标记扩展](dynamicresource-markup-extension.md)
