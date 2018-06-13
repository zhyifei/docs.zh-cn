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
ms.openlocfilehash: 978c97b8cae24bff4ebdea8f4e56a940e5907fa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548761"
---
# <a name="drawing-formatted-text"></a>绘制格式化文本
本主题提供的功能的概述<xref:System.Windows.Media.FormattedText>对象。 此对象为在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中绘制文本提供低级别控制。  
  
  
## <a name="technology-overview"></a>技术概述  
 <xref:System.Windows.Media.FormattedText>对象允许你绘制多行文本，在其中每个字符文本中的可以单独设置格式。 下例演示应用了多种格式的文本。  
  
 ![使用 FormattedText 对象显示的文本](../../../../docs/framework/wpf/advanced/media/formattedtext01.jpg "FormattedText01")  
使用 FormattedText 方法显示的文本  
  
> [!NOTE]
>  对于从 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] API 迁移的开发人员，[Win32 迁移](#win32_migration)一节中的表列出了 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 标志和 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的近似等效项。  
  
### <a name="reasons-for-using-formatted-text"></a>使用格式化文本的原因  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 包括多个用于在屏幕中绘制文本的控件。 每个控件都面向不同的方案，并具有自己的功能和限制列表。 一般情况下，<xref:System.Windows.Controls.TextBlock>有限的文本支持是必需的如中的简短句子时应使用元素[!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)]。 <xref:System.Windows.Controls.Label> 可在时极少的文字支持是必需的。 有关详细信息，请参阅 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)。  
  
 <xref:System.Windows.Media.FormattedText>对象提供了更大的文本格式功能比[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]文本控件，并在你想要将文本用作装饰性元素的情况下可能很有用。 有关详细信息，请参阅下一节[将格式化文本转换为几何图形](#converting_formatted_text)。  
  
 此外，<xref:System.Windows.Media.FormattedText>对象可用于创建面向文本的<xref:System.Windows.Media.DrawingVisual>-派生的对象。 <xref:System.Windows.Media.DrawingVisual> 是用于呈现形状、 图像或文本的轻量绘制类。 有关详细信息，请参阅[使用 DrawingVisuals 执行测试示例](http://go.microsoft.com/fwlink/?LinkID=159994)。  
  
## <a name="using-the-formattedtext-object"></a>使用 FormattedText 对象  
 若要创建带格式的文本，请调用<xref:System.Windows.Media.FormattedText.%23ctor%2A>构造函数来创建<xref:System.Windows.Media.FormattedText>对象。 创建初始格式化文本字符串后，便可应用某一范围的格式样式。  
  
 使用<xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>属性可以将约束到特定的宽度的文本。 文本将自动换行，避免超过指定宽度。 使用<xref:System.Windows.Media.FormattedText.MaxTextHeight%2A>属性来限制为特定高度的文本。 超过指定高度的文本将显示一个省略号“…”。  
  
 ![使用 FormattedText 对象显示的文本](../../../../docs/framework/wpf/advanced/media/formattedtext02.png "FormattedText02")  
显示自动换行和省略号的文本  
  
 可向一个或多个字符应用多种格式样式。 例如，您可以调用<xref:System.Windows.Media.FormattedText.SetFontSize%2A>和<xref:System.Windows.Media.FormattedText.SetForegroundBrush%2A>方法来更改格式设置的文本中的前五个字符。  
  
 下面的代码示例创建<xref:System.Windows.Media.FormattedText>对象，然后将几种格式设置样式应用于的文本。  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets1)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets1)]  
  
### <a name="font-size-unit-of-measure"></a>字号度量单位  
 中的其他文本对象与[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序，<xref:System.Windows.Media.FormattedText>对象使用作为度量单位的独立于设备的像素为单位。 但是，大多数 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 应用程序使用点作为度量单位。 如果要在 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 应用程序中以点为单位显示文本，需要将 [!INCLUDE[TLA#tla_dipixel#plural](../../../../includes/tlasharptla-dipixelsharpplural-md.md)] 转换为点。 以下代码示例演示如何执行此转换。  
  
 [!code-csharp[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FormattedTextSnippets/CSharp/Window1.xaml.cs#formattedtextsnippets2)]
 [!code-vb[FormattedTextSnippets#FormattedTextSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FormattedTextSnippets/visualbasic/window1.xaml.vb#formattedtextsnippets2)]  
  
<a name="converting_formatted_text"></a>   
### <a name="converting-formatted-text-to-a-geometry"></a>将格式化文本转换为几何图形  
 你可以将转换到的格式化的文本<xref:System.Windows.Media.Geometry>对象，使你可以创建其他类型的直观地关注的文本。 例如，你可以创建<xref:System.Windows.Media.Geometry>对象基于轮廓的文本字符串。  
  
 ![使用线性渐变画笔的文本轮廓](../../../../docs/framework/wpf/advanced/media/outlinedtext02.jpg "OutlinedText02")  
使用线性渐变画笔的文本轮廓  
  
 以下示例说明了几种通过修改已转换文本的笔划、填充和突出显示来创建悦目的视觉效果的方法。  
  
 ![对填充和笔画使用不同颜色的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext03.jpg "OutlinedText03")  
将笔划和填充设置为不同颜色的示例  
  
 ![笔画应用了图像画笔的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext04.jpg "OutlinedText04")  
笔划应用了图像画笔的示例  
  
 ![笔画应用了图像画笔的文本](../../../../docs/framework/wpf/advanced/media/outlinedtext05.jpg "OutlinedText05")  
笔划和突出显示应用了图像画笔的示例  
  
 当文本转换为<xref:System.Windows.Media.Geometry>对象，它不再是字符的集合，无法修改的文本字符串中的字符。 但是，可修改已转换文本的笔划和填充属性，以此来影响该文本的外观。 笔划是指已转换文本的轮廓；填充是指已转换文本的轮廓的内部区域。 有关详细信息，请参阅[创建轮廓文本](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md)。  
  
 此外可以将转换到的格式化的文本<xref:System.Windows.Media.PathGeometry>对象，并突出显示文本中使用此对象。 例如，可以应用到动画<xref:System.Windows.Media.PathGeometry>对象，以便让此动画沿着轮廓的带格式的文本。  
  
 下面的示例演示已转换为的格式化的文本<xref:System.Windows.Media.PathGeometry>对象。 经过动画处理的椭圆会沿着所呈现文本的笔划路径显示。  
  
 ![沿着文本路径几何图形运动球](../../../../docs/framework/wpf/advanced/media/textpathgeometry01.gif "TextPathGeometry01")  
沿着文本路径几何图形运动的球  
  
 有关详细信息，请参阅[如何：为文本创建 PathGeometry 动画](http://msdn.microsoft.com/library/29f8051e-798a-463f-a926-a099a99e9c67)。  
  
 已转换为后，你可以创建其他有趣用于格式化文本<xref:System.Windows.Media.PathGeometry>对象。 例如，可剪辑视频，以便在格式化文本中显示。  
  
 ![文本路径几何图形中的视频显示](../../../../docs/framework/wpf/advanced/media/videotextdemo01.png "VideoTextDemo01")  
文本路径几何图形中的视频显示  
  
<a name="win32_migration"></a>   
## <a name="win32-migration"></a>Win32 迁移  
 功能<xref:System.Windows.Media.FormattedText>绘制文本的相近的功能的[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]DrawText 函数。 对于从 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] API 迁移的开发人员，下表列出了 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] DrawText 标志和 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 中的近似等效项。  
  
|DrawText 标志|WPF 等效项|说明|  
|-------------------|--------------------|-----------|  
|DT_BOTTOM|<xref:System.Windows.Media.FormattedText.Height%2A>|使用<xref:System.Windows.Media.FormattedText.Height%2A>属性来计算适当[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]DrawText y 位置。|  
|DT_CALCRECT|<xref:System.Windows.Media.FormattedText.Height%2A>, <xref:System.Windows.Media.FormattedText.Width%2A>|使用<xref:System.Windows.Media.FormattedText.Height%2A>和<xref:System.Windows.Media.FormattedText.Width%2A>属性来计算输出矩形。|  
|DT_CENTER|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|使用<xref:System.Windows.Media.FormattedText.TextAlignment%2A>属性值设置为<xref:System.Windows.TextAlignment.Center>。|  
|DT_EDITCONTROL|无|不要求。 间距宽度和最后一行的呈现与框架编辑控件中的相同。|  
|DT_END_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|使用<xref:System.Windows.Media.FormattedText.Trimming%2A>属性的值<xref:System.Windows.TextTrimming.CharacterEllipsis>。<br /><br /> 使用<xref:System.Windows.TextTrimming.WordEllipsis>获取[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]与 DT_WORD_ELIPSIS DT_END_ELLIPSIS 结束省略号 — 在这种情况下，字符省略号仅出现在单独的行不适合的单词。|  
|DT_EXPAND_TABS|无|不要求。 制表符自动扩展为在每 4 个 em 后停止，这大约为 8 个与语言无关的字符的宽度。|  
|DT_EXTERNALLEADING|无|不要求。 行距中始终包括外部间隙。 使用<xref:System.Windows.Media.FormattedText.LineHeight%2A>属性来创建用户定义的行距。|  
|DT_HIDEPREFIX|无|不支持。 构造之前，删除 & 从字符串<xref:System.Windows.Media.FormattedText>对象。|  
|DT_LEFT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|这是默认文本对齐方式。 使用<xref:System.Windows.Media.FormattedText.TextAlignment%2A>属性值设置为<xref:System.Windows.TextAlignment.Left>。 （仅限 WPF）|  
|DT_MODIFYSTRING|无|不支持。|  
|DT_NOCLIP|<xref:System.Windows.Media.Visual.VisualClip%2A>|剪辑不会自动发生。 如果你愿意剪辑文本，请使用<xref:System.Windows.Media.Visual.VisualClip%2A>属性。|  
|DT_NOFULLWIDTHCHARBREAK|无|不支持。|  
|DT_NOPREFIX|无|不要求。 字符串中的“&”字符始终作为正常字符处理。|  
|DT_PATHELLIPSIS|无|使用<xref:System.Windows.Media.FormattedText.Trimming%2A>属性的值<xref:System.Windows.TextTrimming.WordEllipsis>。|  
|DT_PREFIX|无|不支持。 如果你想要使用下划线的文本，快捷键或链接，例如使用<xref:System.Windows.Media.FormattedText.SetTextDecorations%2A>方法。|  
|DT_PREFIXONLY|无|不支持。|  
|DT_RIGHT|<xref:System.Windows.Media.FormattedText.TextAlignment%2A>|使用<xref:System.Windows.Media.FormattedText.TextAlignment%2A>属性值设置为<xref:System.Windows.TextAlignment.Right>。 （仅限 WPF）|  
|DT_RTLREADING|<xref:System.Windows.Media.FormattedText.FlowDirection%2A>|将 <xref:System.Windows.Media.FormattedText.FlowDirection%2A> 属性设置为 <xref:System.Windows.FlowDirection.RightToLeft>。|  
|DT_SINGLELINE|无|不要求。 <xref:System.Windows.Media.FormattedText> 对象的行为作为单个行控件，除非任一<xref:System.Windows.Media.FormattedText.MaxTextWidth%2A>设置属性或文本包含回车符/换行符 (CR/LF)。|  
|DT_TABSTOP|无|不支持用户定义的制表位位置。|  
|DT_TOP|<xref:System.Windows.Media.FormattedText.Height%2A>|不要求。 上对齐是默认设置。 可以使用定义其他垂直定位值<xref:System.Windows.Media.FormattedText.Height%2A>属性来计算适当[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]DrawText y 位置。|  
|DT_VCENTER|<xref:System.Windows.Media.FormattedText.Height%2A>|使用<xref:System.Windows.Media.FormattedText.Height%2A>属性来计算适当[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]DrawText y 位置。|  
|DT_WORDBREAK|无|不要求。 断字进行自动处理<xref:System.Windows.Media.FormattedText>对象。 无法禁用它。|  
|DT_WORD_ELLIPSIS|<xref:System.Windows.Media.FormattedText.Trimming%2A>|使用<xref:System.Windows.Media.FormattedText.Trimming%2A>属性的值<xref:System.Windows.TextTrimming.WordEllipsis>。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Media.FormattedText>  
 [WPF 中的文档](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [WPF 中的版式](../../../../docs/framework/wpf/advanced/typography-in-wpf.md)  
 [创建空心文本](../../../../docs/framework/wpf/advanced/how-to-create-outlined-text.md)  
 [如何：为文本创建 PathGeometry 动画](http://msdn.microsoft.com/library/29f8051e-798a-463f-a926-a099a99e9c67)
