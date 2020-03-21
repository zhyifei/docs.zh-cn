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
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="47309-102">如何：创建文本修饰</span><span class="sxs-lookup"><span data-stu-id="47309-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="47309-103">对象<xref:System.Windows.TextDecoration>是可以添加到文本的视觉修饰。</span><span class="sxs-lookup"><span data-stu-id="47309-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="47309-104">有四种类型的文本修饰：下划线、基线、击穿和过线。</span><span class="sxs-lookup"><span data-stu-id="47309-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="47309-105">下面的示例显示文本修饰相对于文本的位置。</span><span class="sxs-lookup"><span data-stu-id="47309-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 ![文本修饰类型图](./media/how-to-create-a-text-decoration/text-decoration-types.gif)  
  
 <span data-ttu-id="47309-107">要向文本添加文本修饰，请创建对象<xref:System.Windows.TextDecoration>并修改其属性。</span><span class="sxs-lookup"><span data-stu-id="47309-107">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="47309-108">使用<xref:System.Windows.TextDecoration.Location%2A>属性指定文本修饰的显示位置，如下划线。</span><span class="sxs-lookup"><span data-stu-id="47309-108">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="47309-109">使用<xref:System.Windows.TextDecoration.Pen%2A>属性指定文本修饰的外观，如实心填充或渐变颜色。</span><span class="sxs-lookup"><span data-stu-id="47309-109">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="47309-110">如果不为<xref:System.Windows.TextDecoration.Pen%2A>属性指定值，则修饰默认为与文本相同的颜色。</span><span class="sxs-lookup"><span data-stu-id="47309-110">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="47309-111">定义对象<xref:System.Windows.TextDecoration>后，将其添加到所需文本对象<xref:System.Windows.TextDecorations>的集合中。</span><span class="sxs-lookup"><span data-stu-id="47309-111">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="47309-112">下面的示例显示了使用线性渐变画笔和虚线笔进行样式设置的文本修饰。</span><span class="sxs-lookup"><span data-stu-id="47309-112">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 ![采用线性渐变下划线的文本修饰](./media/how-to-create-a-text-decoration/text-decoration-gradient.png)  
  
 <span data-ttu-id="47309-114">该<xref:System.Windows.Documents.Hyperlink>对象是一个内联级流内容元素，允许您在流内容中托管超链接。</span><span class="sxs-lookup"><span data-stu-id="47309-114">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="47309-115">默认情况下，<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象显示下划线。</span><span class="sxs-lookup"><span data-stu-id="47309-115">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="47309-116"><xref:System.Windows.TextDecoration>对象可以执行密集型实例化，尤其是在有许多<xref:System.Windows.Documents.Hyperlink>对象时。</span><span class="sxs-lookup"><span data-stu-id="47309-116"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="47309-117">如果广泛使用<xref:System.Windows.Documents.Hyperlink>元素，则可能需要考虑仅在触发事件（如<xref:System.Windows.ContentElement.MouseEnter>事件）时显示下划线。</span><span class="sxs-lookup"><span data-stu-id="47309-117">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="47309-118">在下面的示例中，"我的 MSN"链接的下划线是动态的 ，它仅在触发<xref:System.Windows.ContentElement.MouseEnter>事件时才出现。</span><span class="sxs-lookup"><span data-stu-id="47309-118">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 ![显示 TextDecoration 的超链接](./media/how-to-create-a-text-decoration/text-decorations-hyperlinks.png)  

 <span data-ttu-id="47309-120">有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。</span><span class="sxs-lookup"><span data-stu-id="47309-120">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="47309-121">示例</span><span class="sxs-lookup"><span data-stu-id="47309-121">Example</span></span>  
 <span data-ttu-id="47309-122">在下面的代码示例中，下划线文本修饰使用默认字体值。</span><span class="sxs-lookup"><span data-stu-id="47309-122">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="47309-123">在下面的代码示例中，使用笔的纯色画笔创建下划线文本修饰。</span><span class="sxs-lookup"><span data-stu-id="47309-123">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="47309-124">在下面的代码示例中，使用虚线笔的线性渐变画笔创建下划线文本修饰。</span><span class="sxs-lookup"><span data-stu-id="47309-124">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="47309-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47309-125">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="47309-126">指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="47309-126">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
