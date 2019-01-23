---
title: 如何：指定是否为超链接添加下划线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 3199bce25d49bb471fe21735ebb919bbb7f5132c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54576949"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="8c16d-102">如何：指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="8c16d-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="8c16d-103"><xref:System.Windows.Documents.Hyperlink>对象是允许您承载流内容中的超链接的内联级流内容元素。</span><span class="sxs-lookup"><span data-stu-id="8c16d-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="8c16d-104">默认情况下<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。</span><span class="sxs-lookup"><span data-stu-id="8c16d-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="8c16d-105"><xref:System.Windows.TextDecoration> 对象可以是占用实例化，特别是当有许多<xref:System.Windows.Documents.Hyperlink>对象。</span><span class="sxs-lookup"><span data-stu-id="8c16d-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="8c16d-106">如果充分利用了<xref:System.Windows.Documents.Hyperlink>元素，您可能会考虑显示下划线，仅当触发事件，如<xref:System.Windows.ContentElement.MouseEnter>事件。</span><span class="sxs-lookup"><span data-stu-id="8c16d-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="8c16d-107">在以下示例中，"我的 MSN"链接的下划线是动态的 — 它时，才显示<xref:System.Windows.ContentElement.MouseEnter>触发事件。</span><span class="sxs-lookup"><span data-stu-id="8c16d-107">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="8c16d-108">![显示 TextDecorations 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="8c16d-108">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="8c16d-109">定义与 TextDecorations 的超链接</span><span class="sxs-lookup"><span data-stu-id="8c16d-109">Hyperlinks defined with TextDecorations</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c16d-110">示例</span><span class="sxs-lookup"><span data-stu-id="8c16d-110">Example</span></span>  
 <span data-ttu-id="8c16d-111">以下标记示例演示<xref:System.Windows.Documents.Hyperlink>使用和不使用下划线定义：</span><span class="sxs-lookup"><span data-stu-id="8c16d-111">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="8c16d-112">下面的代码示例演示如何创建为下划线<xref:System.Windows.Documents.Hyperlink>上<xref:System.Windows.ContentElement.MouseEnter>事件，并将其上删除<xref:System.Windows.ContentElement.MouseLeave>事件。</span><span class="sxs-lookup"><span data-stu-id="8c16d-112">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="8c16d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c16d-113">See also</span></span>
- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="8c16d-114">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="8c16d-114">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)
- [<span data-ttu-id="8c16d-115">创建文本效果</span><span class="sxs-lookup"><span data-stu-id="8c16d-115">Create a Text Decoration</span></span>](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
