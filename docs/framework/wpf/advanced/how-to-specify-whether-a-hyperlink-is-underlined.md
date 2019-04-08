---
title: 如何：指定是否为超链接添加下划线
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Hyperlink control type [WPF]
ms.assetid: 3996cfe6-1dac-4835-aeb3-c719ce9cfee5
ms.openlocfilehash: 5718912e24a0697f209669b0ab4e7f4df1765ed3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076310"
---
# <a name="how-to-specify-whether-a-hyperlink-is-underlined"></a><span data-ttu-id="2757a-102">如何：指定是否为超链接添加下划线</span><span class="sxs-lookup"><span data-stu-id="2757a-102">How to: Specify Whether a Hyperlink is Underlined</span></span>
<span data-ttu-id="2757a-103"><xref:System.Windows.Documents.Hyperlink>对象是允许您承载流内容中的超链接的内联级流内容元素。</span><span class="sxs-lookup"><span data-stu-id="2757a-103">The <xref:System.Windows.Documents.Hyperlink> object is an inline-level flow content element that allows you to host hyperlinks within the flow content.</span></span> <span data-ttu-id="2757a-104">默认情况下<xref:System.Windows.Documents.Hyperlink>使用<xref:System.Windows.TextDecoration>对象来显示下划线。</span><span class="sxs-lookup"><span data-stu-id="2757a-104">By default, <xref:System.Windows.Documents.Hyperlink> uses a <xref:System.Windows.TextDecoration> object to display an underline.</span></span> <xref:System.Windows.TextDecoration> <span data-ttu-id="2757a-105">对象可以是占用实例化，特别是当有许多<xref:System.Windows.Documents.Hyperlink>对象。</span><span class="sxs-lookup"><span data-stu-id="2757a-105">objects can be performance intensive to instantiate, particularly if you have many <xref:System.Windows.Documents.Hyperlink> objects.</span></span> <span data-ttu-id="2757a-106">如果充分利用了<xref:System.Windows.Documents.Hyperlink>元素，您可能会考虑显示下划线，仅当触发事件，如<xref:System.Windows.ContentElement.MouseEnter>事件。</span><span class="sxs-lookup"><span data-stu-id="2757a-106">If you make extensive use of <xref:System.Windows.Documents.Hyperlink> elements, you may want to consider showing an underline only when triggering an event, such as the <xref:System.Windows.ContentElement.MouseEnter> event.</span></span>  
  
 <span data-ttu-id="2757a-107">在以下示例中，"我的 MSN"链接的下划线是动态的也就是说，它时，才显示<xref:System.Windows.ContentElement.MouseEnter>触发事件。</span><span class="sxs-lookup"><span data-stu-id="2757a-107">In the following example, the underline for the "My MSN" link is dynamic, that is, it only appears when the <xref:System.Windows.ContentElement.MouseEnter> event is triggered.</span></span>  
  
  ![显示 TextDecoration 的超链接](./media/how-to-specify-whether-a-hyperlink-is-underlined/text-decorations-hyperlinks.png)  

## <a name="example"></a><span data-ttu-id="2757a-109">示例</span><span class="sxs-lookup"><span data-stu-id="2757a-109">Example</span></span>  
 <span data-ttu-id="2757a-110">以下标记示例演示<xref:System.Windows.Documents.Hyperlink>使用和不使用下划线定义：</span><span class="sxs-lookup"><span data-stu-id="2757a-110">The following markup sample shows a <xref:System.Windows.Documents.Hyperlink> defined with and without an underline:</span></span>  
  
 [!code-xaml[Performance#PerformanceSnippet11](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml#performancesnippet11)]  
  
 <span data-ttu-id="2757a-111">下面的代码示例演示如何创建为下划线<xref:System.Windows.Documents.Hyperlink>上<xref:System.Windows.ContentElement.MouseEnter>事件，并将其上删除<xref:System.Windows.ContentElement.MouseLeave>事件。</span><span class="sxs-lookup"><span data-stu-id="2757a-111">The following code sample shows how to create an underline for the <xref:System.Windows.Documents.Hyperlink> on the <xref:System.Windows.ContentElement.MouseEnter> event, and remove it on the <xref:System.Windows.ContentElement.MouseLeave> event.</span></span>  
  
 [!code-csharp[Performance#PerformanceSnippet15](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/Hyperlink.xaml.cs#performancesnippet15)]
 [!code-vb[Performance#PerformanceSnippet15](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Performance/visualbasic/hyperlink.xaml.vb#performancesnippet15)]  
  
## <a name="see-also"></a><span data-ttu-id="2757a-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2757a-112">See also</span></span>

- <xref:System.Windows.TextDecoration>
- <xref:System.Windows.Documents.Hyperlink>
- [<span data-ttu-id="2757a-113">优化 WPF 应用程序性能</span><span class="sxs-lookup"><span data-stu-id="2757a-113">Optimizing WPF Application Performance</span></span>](optimizing-wpf-application-performance.md)
- [<span data-ttu-id="2757a-114">创建文本修饰</span><span class="sxs-lookup"><span data-stu-id="2757a-114">Create a Text Decoration</span></span>](how-to-create-a-text-decoration.md)
