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
ms.openlocfilehash: a142604fdb36ec6f85e9411b37077bfffff587d4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363912"
---
# <a name="how-to-create-a-text-decoration"></a><span data-ttu-id="01b1e-102">如何：创建文本修饰</span><span class="sxs-lookup"><span data-stu-id="01b1e-102">How to: Create a Text Decoration</span></span>
<span data-ttu-id="01b1e-103">一个<xref:System.Windows.TextDecoration>对象是可以添加到文本的视觉装饰。</span><span class="sxs-lookup"><span data-stu-id="01b1e-103">A <xref:System.Windows.TextDecoration> object is a visual ornamentation you can add to text.</span></span> <span data-ttu-id="01b1e-104">有四种类型的文本修饰： 下划线、 基线、 删除线和上划线。</span><span class="sxs-lookup"><span data-stu-id="01b1e-104">There are four types of text decorations: underline, baseline, strikethrough, and overline.</span></span> <span data-ttu-id="01b1e-105">下面的示例显示了文本修饰相对于文本的位置。</span><span class="sxs-lookup"><span data-stu-id="01b1e-105">The following example shows the locations of the text decorations relative to the text.</span></span>  
  
 <span data-ttu-id="01b1e-106">![文本修饰位置示意图](./media/textdecoration01.gif "TextDecoration01")</span><span class="sxs-lookup"><span data-stu-id="01b1e-106">![Diagram of text decoration locations](./media/textdecoration01.gif "TextDecoration01")</span></span>  
<span data-ttu-id="01b1e-107">文本修饰类型的示例</span><span class="sxs-lookup"><span data-stu-id="01b1e-107">Example of text decoration types</span></span>  
  
 <span data-ttu-id="01b1e-108">若要将文本修饰添加到文本中，创建<xref:System.Windows.TextDecoration>对象，并修改其属性。</span><span class="sxs-lookup"><span data-stu-id="01b1e-108">To add a text decoration to text, create a <xref:System.Windows.TextDecoration> object and modify its properties.</span></span> <span data-ttu-id="01b1e-109">使用<xref:System.Windows.TextDecoration.Location%2A>属性来指定文本修饰的显示位置，如下划线。</span><span class="sxs-lookup"><span data-stu-id="01b1e-109">Use the <xref:System.Windows.TextDecoration.Location%2A> property to specify where the text decoration appears, such as underline.</span></span> <span data-ttu-id="01b1e-110">使用<xref:System.Windows.TextDecoration.Pen%2A>属性来指定文本修饰，如纯色填充或渐变颜色的外观。</span><span class="sxs-lookup"><span data-stu-id="01b1e-110">Use the <xref:System.Windows.TextDecoration.Pen%2A> property to specify the appearance of the text decoration, such as a solid fill or gradient color.</span></span> <span data-ttu-id="01b1e-111">如果未指定的值<xref:System.Windows.TextDecoration.Pen%2A>属性，为相同的颜色为文本修饰默认值。</span><span class="sxs-lookup"><span data-stu-id="01b1e-111">If you do not specify a value for the <xref:System.Windows.TextDecoration.Pen%2A> property, the decorations defaults to the same color as the text.</span></span> <span data-ttu-id="01b1e-112">定义后<xref:System.Windows.TextDecoration>对象，将其添加到<xref:System.Windows.TextDecorations>所需的文本对象的集合。</span><span class="sxs-lookup"><span data-stu-id="01b1e-112">Once you have defined a <xref:System.Windows.TextDecoration> object, add it to the <xref:System.Windows.TextDecorations> collection of the desired text object.</span></span>  
  
 <span data-ttu-id="01b1e-113">下面的示例演示了样式使用线性渐变画笔和虚线的笔的文本修饰。</span><span class="sxs-lookup"><span data-stu-id="01b1e-113">The following example shows a text decoration that has been styled with a linear gradient brush and a dashed pen.</span></span>  
  
 <span data-ttu-id="01b1e-114">![采用线性渐变下划线的文本修饰](./media/textdecoration02.png "TextDecoration02")</span><span class="sxs-lookup"><span data-stu-id="01b1e-114">![Text decoration with linear gradient underline](./media/textdecoration02.png "TextDecoration02")</span></span>  
<span data-ttu-id="01b1e-115">示例中的下划线的样式使用线性渐变画笔和虚线的钢笔</span><span class="sxs-lookup"><span data-stu-id="01b1e-115">Example of an underline styled with a linear gradient brush and dashed pen</span></span>  
  
 <span data-ttu-id="01b1e-116"><xref:System.Windows.Documents.Hyperlink>对象是允许您承载流内容中的超链接的内联级流内容元素。</span><span class="sxs-lookup"><span data-stu-id="01b1e-116">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="01b1e-117">默认情况下<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。</span><span class="sxs-lookup"><span data-stu-id="01b1e-117">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="01b1e-118"><xref:System.Windows.TextDecoration> 对象可以是占用实例化，特别是当有许多<xref:System.Windows.Documents.Hyperlink>对象。</span><span class="sxs-lookup"><span data-stu-id="01b1e-118"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="01b1e-119">如果充分利用了<xref:System.Windows.Documents.Hyperlink>元素，您可能会考虑显示下划线，仅当触发事件，如<xref:System.Windows.ContentElement.MouseEnter>事件。</span><span class="sxs-lookup"><span data-stu-id="01b1e-119">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="01b1e-120">在以下示例中，"我的 MSN"链接的下划线是动态的 — 它时，才显示<xref:System.Windows.ContentElement.MouseEnter>触发事件。</span><span class="sxs-lookup"><span data-stu-id="01b1e-120">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="01b1e-121">![显示 TextDecorations 的超](./media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="01b1e-121">![Hyperlinks displaying TextDecorations](./media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="01b1e-122">定义与 TextDecorations 的超链接</span><span class="sxs-lookup"><span data-stu-id="01b1e-122">Hyperlinks defined with TextDecorations</span></span>  
  
 <span data-ttu-id="01b1e-123">有关详细信息，请参阅[指定是否为超链接添加下划线](how-to-specify-whether-a-hyperlink-is-underlined.md)。</span><span class="sxs-lookup"><span data-stu-id="01b1e-123">For more information, see [Specify Whether a Hyperlink is Underlined](how-to-specify-whether-a-hyperlink-is-underlined.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01b1e-124">示例</span><span class="sxs-lookup"><span data-stu-id="01b1e-124">Example</span></span>  
 <span data-ttu-id="01b1e-125">在下面的代码示例中，下划线文本修饰使用的默认字体值。</span><span class="sxs-lookup"><span data-stu-id="01b1e-125">In the following code example, an underline text decoration uses the default font value.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets1)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets1)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets1)]  
  
 <span data-ttu-id="01b1e-126">下面的代码示例，笔纯色画笔创建下划线文本修饰。</span><span class="sxs-lookup"><span data-stu-id="01b1e-126">In the following code example, an underline text decoration is created with a solid color brush for the pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets2)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets2)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets2)]  
  
 <span data-ttu-id="01b1e-127">以下代码示例中，虚线笔线性渐变画笔创建下划线文本修饰。</span><span class="sxs-lookup"><span data-stu-id="01b1e-127">In the following code example, an underline text decoration is created with a linear gradient brush for the dashed pen.</span></span>  
  
 [!code-csharp[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml.cs#textdecorationsnippets3)]
 [!code-vb[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextDecorationSnippets/visualbasic/window1.xaml.vb#textdecorationsnippets3)]
 [!code-xaml[TextDecorationSnippets#TextDecorationSnippets3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextDecorationSnippets/CSharp/Window1.xaml#textdecorationsnippets3)]  
  
## <a name="see-also"></a><span data-ttu-id="01b1e-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="01b1e-128">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="01b1e-129">指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="01b1e-129">Specify Whether a Hyperlink is Underlined</span></span>](how-to-specify-whether-a-hyperlink-is-underlined.md)
