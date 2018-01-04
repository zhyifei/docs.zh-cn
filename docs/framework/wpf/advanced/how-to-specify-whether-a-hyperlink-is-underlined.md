---
title: "如何：指定是否为超链接添加下划线"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 24c3cc1bba4fd12d4a0f2ad02fa0c1b52b124381
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="5a400-102">如何：指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="5a400-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="5a400-103"><xref:System.Windows.Documents.Hyperlink>对象是允许你在流内容中承载超链接的内联级别流内容元素。</span><span class="sxs-lookup"><span data-stu-id="5a400-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="5a400-104">默认情况下，<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。</span><span class="sxs-lookup"><span data-stu-id="5a400-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <span data-ttu-id="5a400-105"><xref:System.Windows.TextDecoration>对象可以是实例化，大幅降低性能，特别是当你有许多<xref:System.Windows.Documents.Hyperlink>对象。</span><span class="sxs-lookup"><span data-stu-id="5a400-105"><xref:System.Windows.TextDecoration> objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="5a400-106">如果你进行大量使用<xref:System.Windows.Documents.Hyperlink>元素，你可能想要显示下划线，仅当如触发事件时，请考虑<xref:System.Windows.ContentElement.MouseEnter>事件。</span><span class="sxs-lookup"><span data-stu-id="5a400-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="5a400-107">在下面的示例中，"我 MSN"链接的下划线是动态的 — 它只会显示时<xref:System.Windows.ContentElement.MouseEnter>触发事件。</span><span class="sxs-lookup"><span data-stu-id="5a400-107">In the following example, the underline for the "My MSN" link is dynamic—it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
 <span data-ttu-id="5a400-108">![显示 Textdecoration 的超](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span><span class="sxs-lookup"><span data-stu-id="5a400-108">![Hyperlinks displaying TextDecorations](../../../../docs/framework/wpf/advanced/media/textdecoration03.png "TextDecoration03")</span></span>  
<span data-ttu-id="5a400-109">定义与 Textdecoration 的超链接</span><span class="sxs-lookup"><span data-stu-id="5a400-109">Hyperlinks defined with TextDecorations</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a400-110">示例</span><span class="sxs-lookup"><span data-stu-id="5a400-110">Example</span></span>  
 <span data-ttu-id="5a400-111">下面的标记示例演示<xref:System.Windows.Documents.Hyperlink>使用和未使用下划线定义：</span><span class="sxs-lookup"><span data-stu-id="5a400-111">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="5a400-112">下面的代码示例演示如何创建为下划线<xref:System.Windows.Documents.Hyperlink>上<xref:System.Windows.ContentElement.MouseEnter>事件，并将其删除上<xref:System.Windows.ContentElement.MouseLeave>事件。</span><span class="sxs-lookup"><span data-stu-id="5a400-112">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="5a400-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a400-113">See Also</span></span>  
 <xref:System.Windows.TextDecoration>  
 <xref:System.Windows.Documents.Hyperlink>  
 [<span data-ttu-id="5a400-114">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="5a400-114">Optimizing WPF Application Performance</span></span>](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [<span data-ttu-id="5a400-115">创建文本效果</span><span class="sxs-lookup"><span data-stu-id="5a400-115">Create a Text Decoration</span></span>](../../../../docs/framework/wpf/advanced/how-to-create-a-text-decoration.md)
