---
title: 如何：创建文本修饰
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [WPF], baseline
- text [WPF], decorations
- fonts [WPF], underline
- fonts [WPF], overline
- strikethrough type [WPF]
- fonts [WPF], strikethrough
- overline type [WPF]
- underline type [WPF]
- typography [WPF], text decorations
- baseline type [WPF]
ms.assetid: cf3cb4e7-782a-4be7-b2d4-e0935e21e4e0
ms.openlocfilehash: c16073dd2413c1258f4875ac4118e0656d29b171
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545404"
---
# <a name="how-to-create-a-text-decoration"></a>如何：创建文本修饰
A<xref:System.Windows.TextDecoration>对象是你可以将其添加到文本的视觉装饰。 文本修饰的四种类型： 下划线、 基线、 删除线和上划线。 下面的示例显示相对于文本的文本修饰的位置。  
  
 ![文本修饰位置示意图](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")  
文本修饰类型的示例  
  
 若要将文本效果添加到文本中，创建<xref:System.Windows.TextDecoration>对象，并修改其属性。 使用<xref:System.Windows.TextDecoration.Location%2A>属性指定在文本效果本出现的位置，如下划线。 使用<xref:System.Windows.TextDecoration.Pen%2A>属性指定的文本效果，如纯色填充或渐变颜色的外观。 如果未指定的值<xref:System.Windows.TextDecoration.Pen%2A>属性，则修饰默认为文本与相同的颜色。 一旦定义<xref:System.Windows.TextDecoration>对象，请将其添加到<xref:System.Windows.TextDecorations>所需的文本对象的集合。  
  
 下面的示例演示用线性渐变画笔和虚线的钢笔设计的文本修饰。  
  
 ![采用线性渐变下划线的文本效果](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")  
示例中的下划线的风格使用线性渐变画笔和虚线的钢笔  
  
 <xref:System.Windows.Documents.Hyperlink>对象是允许你在流内容中承载超链接的内联级别流内容元素。 默认情况下，<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。 <xref:System.Windows.TextDecoration> 对象可以是实例化，大幅降低性能，特别是当你有许多<xref:System.Windows.Documents.Hyperlink>对象。 如果你进行大量使用<xref:System.Windows.Documents.Hyperlink>元素，你可能想要显示下划线，仅当如触发事件时，请考虑<xref:System.Windows.ContentElement.MouseEnter>事件。  
  
 在下面的示例中，"我 MSN"链接的下划线是动态的 — 它只会显示时<xref:System.Windows.ContentElement.MouseEnter>触发事件。  
  
 ![显示 Textdecoration 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")  
定义与 Textdecoration 的超链接  
  
 有关详细信息，请参阅[指定是否为超链接添加下划线](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)。  
  
## <a name="example"></a>示例  
 在下面的代码示例中，下划线文本修饰使用的默认字体值。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 在下面的代码示例中，下划线文本修饰创建钢笔的纯色画笔。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 下面的代码示例中，使用虚线钢笔的线性渐变画笔创建下划线文本修饰。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [指定是否为超链接添加下划线](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
