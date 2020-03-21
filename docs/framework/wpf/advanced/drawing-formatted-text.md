---
title: 绘制格式化文本
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF]
- typography [WPF], drawing formatted text
- formatted text [WPF]
- drawing [WPF], formatted text
ms.assetid: b1d851c1-331c-4814-9964-6fe769db6f1f
ms.openlocfilehash: 1e82795afbdd5b1b0a05f95600ebdb92fc134b7d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186564"
---
# <a name="drawing-formatted-text"></a>绘制格式化文本
本主题概述了<xref:System.Windows.Media.FormattedText>对象的功能。 此对象为在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中绘制文本提供低级别控制。  

## <a name="technology-overview"></a>技术概述  
 该<xref:System.Windows.Media.FormattedText>对象允许您绘制多行文本，其中文本中的每个字符都可以单独设置格式。 下例演示应用了多种格式的文本。  
  
 ![使用 FormattedText 对象显示的文本](./media/typography-in-wpf/text-formatted-linear-gradient.jpg)  
  
> [!NOTE]
> 对于从 Win32 API 迁移的开发人员[，Win32 迁移](#win32_migration)部分中的表列出了 Win32 DrawText 标志和 中的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]近似等效标志。  
  
### <a name="reasons-for-using-formatted-text"></a>使用格式化文本的原因  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。 通常，当需要<xref:System.Windows.Controls.TextBlock>有限的文本支持时，应使用元素，例如 中的[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]简短句子。 <xref:System.Windows.Controls.Label>可在需要最少的文本支持时使用。 有关详细信息，请参阅 [WPF 中的文档](documents-in-wpf.md)。  
  
 该<xref:System.Windows.Media.FormattedText>对象提供的文本格式功能比[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]文本控件更大，并且在希望将文本用作装饰元素的情况下非常有用。 有关详细信息，请参阅下一节[将格式化文本转换为几何图形](#converting_formatted_text)。  
  
 此外，该<xref:System.Windows.Media.FormattedText>对象可用于创建面向<xref:System.Windows.Media.DrawingVisual>文本的派生对象。 <xref:System.Windows.Media.DrawingVisual>是用于渲染形状、图像或文本的轻量级绘图类。 有关详细信息，请参阅[使用 DrawingVisuals 执行测试示例](https://github.com/Microsoft/WPF-Samples/tree/master/Visual%20Layer/DrawingVisual)。  
  
## <a name="using-the-formattedtext-object"></a>使用 FormattedText 对象  
 要创建格式化的文本，<xref:System.Windows.Media.FormattedText.%23ctor%2A>请调用构造函数以创建对象。 <xref:System.Windows.Media.FormattedText> 创建初始格式化文本字符串后，便可应用某一范围的格式样式。  
  
 使用<xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>属性将文本限制为特定宽度。 文本将自动换行，避免超过指定宽度。 使用<xref:System.Windows.Media.FormattedText.MaxTextHeight%2A>属性将文本限制到特定高度。 超过指定高度的文本将显示一个省略号“…”。  
  
 ![显示带有字包和省略号的文本。](./media/drawing-formatted-text/formatted-text-wordwrap-ellipsis.png)
  
 可向一个或多个字符应用多种格式样式。 例如，可以同时调用 和<xref:System.Windows.Media.FormattedText.SetFontSize%2A><xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A>方法来更改文本中前五个字符的格式。  
  
 以下代码示例创建一个<xref:System.Windows.Media.FormattedText>对象，然后将多个格式样式应用于文本。  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>字号度量单位  
 与[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中的其他文本对象一样，<xref:System.Windows.Media.FormattedText>对象使用与设备无关的像素作为度量单位。 但是，大多数 Win32 应用程序使用点作为度量单位。 如果要在[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序中以点为单位使用显示文本，则需要将独立于设备的单位（单位 1/96 英寸）转换为点。 以下代码示例演示如何执行此转换。  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>
### <a name="converting-formatted-text-to-a-geometry"></a>将格式化文本转换为几何图形  
 您可以将格式化的文本转换为<xref:System.Windows.Media.Geometry>对象，从而创建其他类型的视觉上有趣的文本。 例如，可以基于文本字符串的<xref:System.Windows.Media.Geometry>轮廓创建对象。  
  
 ![使用线性渐变画笔的文本轮廓](./media/typography-in-wpf/text-outline-linear-gradient.jpg)
  
 以下示例说明了几种通过修改已转换文本的笔划、填充和突出显示来创建悦目的视觉效果的方法。  
  
 ![对填充和笔画使用不同颜色的文本](./media/typography-in-wpf/fill-stroke-text-effect.jpg)  
  
 ![笔画应用了图像画笔的文本](./media/typography-in-wpf/image-brush-application.jpg)
  
 ![应用图像画笔进行描边和高光的文本](./media/typography-in-wpf/image-brush-text-application.jpg)
  
 将文本转换为对象时<xref:System.Windows.Media.Geometry>，它不再是字符的集合，无法修改文本字符串中的字符。 但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。 笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。 有关详细信息，请参阅[创建轮廓文本](how-to-create-outlined-text.md)。  
  
 您还可以将格式化的文本转换为<xref:System.Windows.Media.PathGeometry>对象，并使用该对象突出显示文本。 例如，您可以将动画应用于对象，<xref:System.Windows.Media.PathGeometry>以便动画遵循格式化文本的轮廓。  
  
 下面的示例显示已转换为<xref:System.Windows.Media.PathGeometry>对象的格式化文本。 经过动画处理的椭圆会沿着所呈现文本的笔划路径显示。  
  
 ![沿着文本路径几何图形运动的球](./media/drawing-formatted-text/sphere-following-geometry-path.gif)  
沿着文本路径几何图形运动的球  
  
 有关详细信息，请参阅[如何：为文本创建 PathGeometry 动画](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))。  
  
 将格式化文本转换为<xref:System.Windows.Media.PathGeometry>对象后，可以为它创建其他有趣的用途。 例如，可剪辑视频，以便在格式化文本中显示。  
  
 ![文本路径几何图形中的视频显示](./media/drawing-formatted-text/video-displaying-text-path-geometry.png)
  
<a name="win32_migration"></a>
## <a name="win32-migration"></a>Win32 迁移  
 绘图文本的功能<xref:System.Windows.Media.FormattedText>类似于 Win32 绘制文本功能的功能。 对于从 Win32 API 迁移的开发人员，下表列出了 Win32 DrawText 标志和 中的[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]近似等效标志。  
  
|DrawText 标志|WPF 等效项|说明|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|使用<xref:System.Windows.Media.FormattedText.Height%2A>属性计算适当的 Win32 绘制文本"y"位置。|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|使用<xref:System.Windows.Media.FormattedText.Height%2A>和<xref:System.Windows.Media.FormattedText.Width%2A>属性计算输出矩形。|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|将<xref:System.Windows.Media.FormattedText.TextAlignment%2A>值设置为 的属性使用<xref:System.Windows.TextAlignment.Center>。|  
|DT_EDITCONTROL|无|非必需。 间距宽度和最后一行的呈现与框架编辑控件中的相同。|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|使用<xref:System.Windows.Media.FormattedText.Trimming%2A>具有 值<xref:System.Windows.TextTrimming.CharacterEllipsis>的属性 。<br /><br /> 用于<xref:System.Windows.TextTrimming.WordEllipsis>使用DT_WORD_ELIPSIS端椭圆获取 Win32 DT_END_ELLIPSIS — 在这种情况下，字符省略号仅发生在不适合单行的单词上。|  
|DT_EXPAND_TABS|无|非必需。 制表符自动扩展为在每 4 个 em 后停止，这大约为 8 个与语言无关的字符的宽度。|  
|DT_EXTERNALLEADING|无|非必需。 行距中始终包括外部间隙。 使用<xref:System.Windows.Media.FormattedText.LineHeight%2A>属性创建用户定义的行间距。|  
|DT_HIDEPREFIX|无|不支持。 在构造<xref:System.Windows.Media.FormattedText>对象之前，请从字符串中删除"&"。|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|这是默认文本对齐方式。 将<xref:System.Windows.Media.FormattedText.TextAlignment%2A>值设置为 的属性使用<xref:System.Windows.TextAlignment.Left>。 （仅限 WPF）|  
|DT_MODIFYSTRING|无|不支持。|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|剪辑不会自动发生。 如果要剪辑文本，请使用 属性<xref:System.Windows.Media.Visual.VisualClip%2A>。|  
|DT_NOFULLWIDTHCHARBREAK|无|不支持。|  
|DT_NOPREFIX|无|非必需。 字符串中的“&”字符始终作为正常字符处理。|  
|DT_PATHELLIPSIS|无|使用<xref:System.Windows.Media.FormattedText.Trimming%2A>具有 值<xref:System.Windows.TextTrimming.WordEllipsis>的属性 。|  
|DT_PREFIX|无|不支持。 如果要对文本（如快捷键或链接）使用下划线，请使用 方法<xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>。|  
|DT_PREFIXONLY|无|不支持。|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|将<xref:System.Windows.Media.FormattedText.TextAlignment%2A>值设置为 的属性使用<xref:System.Windows.TextAlignment.Right>。 （仅限 WPF）|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|将 <xref:System.Windows.Media.FormattedText.FlowDirection%2A> 属性设置为 <xref:System.Windows.FlowDirection.RightToLeft>。|  
|DT_SINGLELINE|无|非必需。 <xref:System.Windows.Media.FormattedText>对象作为单行控件行，除非设置<xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>属性或文本包含回车/换行 （CR/LF）。|  
|DT_TABSTOP|无|不支持用户定义的制表位位置。|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|非必需。 上对齐是默认设置。 其他垂直定位值可以通过使用 属性<xref:System.Windows.Media.FormattedText.Height%2A>计算适当的 Win32 DrawText 'y' 位置来定义。|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|使用<xref:System.Windows.Media.FormattedText.Height%2A>属性计算适当的 Win32 绘制文本"y"位置。|  
|DT_WORDBREAK|无|非必需。 <xref:System.Windows.Media.FormattedText>对象会自动发生断字。 无法禁用它。|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|使用<xref:System.Windows.Media.FormattedText.Trimming%2A>具有 值<xref:System.Windows.TextTrimming.WordEllipsis>的属性 。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Media.FormattedText>
- [WPF 中的文档](documents-in-wpf.md)
- [WPF 中的版式](typography-in-wpf.md)
- [创建轮廓文本](how-to-create-outlined-text.md)
- [如何：为文本创建 PathGeometry 动画](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms743610(v=vs.100))
