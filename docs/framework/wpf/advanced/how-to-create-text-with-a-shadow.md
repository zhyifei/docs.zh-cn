---
title: 如何：创建具有阴影的文本
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], shadow effects
- shadow effects in text [WPF]
- text [WPF], shadowed
ms.assetid: 6ab9c754-6001-4708-b479-5367f2fd1a35
ms.openlocfilehash: c3e8135372ce4a092552c812cd971cb70bc49bf3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186849"
---
# <a name="how-to-create-text-with-a-shadow"></a>如何：创建具有阴影的文本
本节中的示例演示如何为所显示的文本创建阴影效果。  
  
## <a name="example"></a>示例  
 该<xref:System.Windows.Media.Effects.DropShadowEffect>对象允许您为[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]对象创建各种投影效果。 以下示例显示了应用于文本的投影效果。 在本例中，阴影是柔和阴影，这意味着阴影颜色模糊化。  
  
 ![具有柔和度&#61; 0.25 的文本阴影](./media/how-to-create-text-with-a-shadow/drop-shadow-text-effect.jpg)
  
 您可以通过设置<xref:System.Windows.Media.Effects.DropShadowEffect.ShadowDepth%2A>属性来控制阴影的宽度。 的值`4.0`表示阴影宽度为 4 像素。 您可以通过修改<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性来控制阴影的柔和度或模糊性。 的值`0.0`表示没有模糊。 以下代码示例演示如何创建柔和阴影。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet1)]  
  
> [!NOTE]
> 这些阴影效果不会通过[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]文本呈现管道。 因此，在使用这些效果时，将禁用 ClearType。  
  
 以下示例显示了应用于文本的硬投影效果。 在此例中，阴影不模糊。  
  
 ![具有柔和性&#61; 0 的文本阴影](./media/how-to-create-text-with-a-shadow/text-shadow-softness.jpg)
  
 通过将<xref:System.Windows.Media.Effects.DropShadowEffect.BlurRadius%2A>属性设置为`0.0`（）来创建硬阴影，该属性指示不使用模糊。 您可以通过修改<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>属性来控制阴影的方向。 将此属性的方向值设置为 和`0``360`之间的程度。 下图显示了属性设置的方向<xref:System.Windows.Media.Effects.DropShadowEffect.Direction%2A>值。  
  
 ![阴影的 DropShadow 程度设置](./media/how-to-create-text-with-a-shadow/drop-shadow-degree-setting.png)
  
 以下代码示例演示如何创建硬阴影。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/SingleShadows.xaml#textshadowsnippet2)]  
  
## <a name="using-a-blur-effect"></a>使用模糊效果  
 <xref:System.Windows.Media.Effects.BlurBitmapEffect>可用于创建可放置在文本对象后面的类似阴影的效果。 应用于文本的模糊位图效果在各个方向上均匀地对文本进行模糊化。  
  
 以下示例显示了应用于文本的模糊效果。  
  
 ![使用 BlurBitmapEffect 的文本阴影](./media/how-to-create-text-with-a-shadow/text-shadow-blur-effect.jpg)  
  
 以下代码示例演示如何创建模糊效果。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet6](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/BlurShadows.xaml#textshadowsnippet6)]  
  
## <a name="using-a-translate-transform"></a>使用转换变换  
 <xref:System.Windows.Media.TranslateTransform>可用于创建可放置在文本对象后面的类似阴影的效果。  
  
 以下代码示例使用 偏移<xref:System.Windows.Media.TranslateTransform>文本。 在本示例中，主要文本下方略微偏移的文本副本营造出了阴影效果。  
  
 ![使用 TranslateTransform 的文本阴影](./media/how-to-create-text-with-a-shadow/text-transform-shadow-effect.jpg)
  
 以下代码示例演示如何创建转换以实现阴影效果。  
  
 [!code-xaml[TextShadowSnippets#TextShadowSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/TextShadowSnippets/CS/TransformShadows.xaml#textshadowsnippet7)]
