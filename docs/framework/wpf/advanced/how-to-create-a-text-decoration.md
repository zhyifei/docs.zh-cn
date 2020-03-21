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
ms.openlocfilehash: cf3b3c3bcb75153a0be4f7ced03b38134b79a930
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185919"
---
# <a name="how-to-create-a-text-decoration"></a>如何：创建文本修饰
对象<xref:System.Windows.TextDecoration>是可以添加到文本的视觉修饰。 有四种类型的文本修饰：下划线、基线、击穿和过线。 下面的示例显示文本修饰相对于文本的位置。  
  
 ![文本修饰类型图](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 要向文本添加文本修饰，请创建对象<xref:System.Windows.TextDecoration>并修改其属性。 使用<xref:System.Windows.TextDecoration.Location%2A>属性指定文本修饰的显示位置，如下划线。 使用<xref:System.Windows.TextDecoration.Pen%2A>属性指定文本修饰的外观，如实心填充或渐变颜色。 如果不为<xref:System.Windows.TextDecoration.Pen%2A>属性指定值，则修饰默认为与文本相同的颜色。 定义对象<xref:System.Windows.TextDecoration>后，将其添加到所需文本对象<xref:System.Windows.TextDecorations>的集合中。  
  
 下面的示例显示了使用线性渐变画笔和虚线笔进行样式设置的文本修饰。  
  
 ![采用线性渐变下划线的文本修饰](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 该<xref:System.Windows.Documents.Hyperlink>对象是一个内联级流内容元素，允许您在流内容中托管超链接。 默认情况下，<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象显示下划线。 <xref:System.Windows.TextDecoration>对象可以执行密集型实例化，尤其是在有许多<xref:System.Windows.Documents.Hyperlink>对象时。 如果广泛使用<xref:System.Windows.Documents.Hyperlink>元素，则可能需要考虑仅在触发事件（如<xref:System.Windows.ContentElement.MouseEnter>事件）时显示下划线。  
  
 在下面的示例中，"我的 MSN"链接的下划线是动态的 ，它仅在触发<xref:System.Windows.ContentElement.MouseEnter>事件时才出现。  
  
 ![显示 TextDecoration 的超链接](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。  
  
## <a name="example"></a>示例  
 在下面的代码示例中，下划线文本修饰使用默认字体值。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 在下面的代码示例中，使用笔的纯色画笔创建下划线文本修饰。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 在下面的代码示例中，使用虚线笔的线性渐变画笔创建下划线文本修饰。  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)
