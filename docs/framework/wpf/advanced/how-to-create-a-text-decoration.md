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
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="bda6b-102">如何：创建文本修饰</span><span class="sxs-lookup"><span data-stu-id="bda6b-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="bda6b-103">A<xref:System.Windows.TextDecoration>对象是你可以将其添加到文本的视觉装饰。</span><span class="sxs-lookup"><span data-stu-id="bda6b-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="bda6b-104">文本修饰的四种类型： 下划线、 基线、 删除线和上划线。</span><span class="sxs-lookup"><span data-stu-id="bda6b-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="bda6b-105">下面的示例显示相对于文本的文本修饰的位置。</span><span class="sxs-lookup"><span data-stu-id="bda6b-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="bda6b-106">![文本修饰位置示意图](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="bda6b-106">![Diagram of text decoration locations](../../../../docs/framework/wpf/advanced/media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="bda6b-107">文本修饰类型的示例</span><span class="sxs-lookup"><span data-stu-id="bda6b-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="bda6b-108">若要将文本效果添加到文本中，创建<xref:System.Windows.TextDecoration>对象，并修改其属性。</span><span class="sxs-lookup"><span data-stu-id="bda6b-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="bda6b-109">使用<xref:System.Windows.TextDecoration.Location%2A>属性指定在文本效果本出现的位置，如下划线。</span><span class="sxs-lookup"><span data-stu-id="bda6b-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="bda6b-110">使用<xref:System.Windows.TextDecoration.Pen%2A>属性指定的文本效果，如纯色填充或渐变颜色的外观。</span><span class="sxs-lookup"><span data-stu-id="bda6b-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="bda6b-111">如果未指定的值<xref:System.Windows.TextDecoration.Pen%2A>属性，则修饰默认为文本与相同的颜色。</span><span class="sxs-lookup"><span data-stu-id="bda6b-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="bda6b-112">一旦定义<xref:System.Windows.TextDecoration>对象，请将其添加到<xref:System.Windows.TextDecorations>所需的文本对象的集合。</span><span class="sxs-lookup"><span data-stu-id="bda6b-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="bda6b-113">下面的示例演示用线性渐变画笔和虚线的钢笔设计的文本修饰。</span><span class="sxs-lookup"><span data-stu-id="bda6b-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="bda6b-114">![采用线性渐变下划线的文本效果](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="bda6b-114">![Text decoration with linear gradient underline](../../../../docs/framework/wpf/advanced/media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="bda6b-115">示例中的下划线的风格使用线性渐变画笔和虚线的钢笔</span><span class="sxs-lookup"><span data-stu-id="bda6b-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="bda6b-116"><xref:System.Windows.Documents.Hyperlink>对象是允许你在流内容中承载超链接的内联级别流内容元素。</span><span class="sxs-lookup"><span data-stu-id="bda6b-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="bda6b-117">默认情况下，<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。</span><span class="sxs-lookup"><span data-stu-id="bda6b-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="bda6b-118"><xref:System.Windows.TextDecoration> 对象可以是实例化，大幅降低性能，特别是当你有许多<xref:System.Windows.Documents.Hyperlink>对象。</span><span class="sxs-lookup"><span data-stu-id="bda6b-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="bda6b-119">如果你进行大量使用<xref:System.Windows.Documents.Hyperlink>元素，你可能想要显示下划线，仅当如触发事件时，请考虑<xref:System.Windows.ContentElement.MouseEnter>事件。</span><span class="sxs-lookup"><span data-stu-id="bda6b-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="bda6b-120">在下面的示例中，"我 MSN"链接的下划线是动态的 — 它只会显示时<xref:System.Windows.ContentElement.MouseEnter>触发事件。</span><span class="sxs-lookup"><span data-stu-id="bda6b-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="bda6b-121">![显示 Textdecoration 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="bda6b-121">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="bda6b-122">定义与 Textdecoration 的超链接</span><span class="sxs-lookup"><span data-stu-id="bda6b-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="bda6b-123">有关详细信息，请参阅[指定是否为超链接添加下划线](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)。</span><span class="sxs-lookup"><span data-stu-id="bda6b-123">For more information, see [Specify Whether a Hyperlink is Underlined](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bda6b-124">示例</span><span class="sxs-lookup"><span data-stu-id="bda6b-124">Example</span></span>  
 <span data-ttu-id="bda6b-125">在下面的代码示例中，下划线文本修饰使用的默认字体值。</span><span class="sxs-lookup"><span data-stu-id="bda6b-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="bda6b-126">在下面的代码示例中，下划线文本修饰创建钢笔的纯色画笔。</span><span class="sxs-lookup"><span data-stu-id="bda6b-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="bda6b-127">下面的代码示例中，使用虚线钢笔的线性渐变画笔创建下划线文本修饰。</span><span class="sxs-lookup"><span data-stu-id="bda6b-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="bda6b-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="bda6b-128">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="bda6b-129">指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="bda6b-129">Specify Whether a Hyperlink is Underlined</span></span>](../../../../docs/framework/wpf/advanced/how-to-specify-whether-a-hyperlink-is-underlined.md)
