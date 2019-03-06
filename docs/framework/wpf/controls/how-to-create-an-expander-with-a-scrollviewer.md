---
title: 如何：使用 ScrollViewer 创建 Expander
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Expander
- ScrollViewer control [WPF], with Expander control
- Expander control [WPF], creating
- controls [WPF], ScrollViewer
ms.assetid: 2ad124d2-2406-4157-aaf2-64e067298f01
ms.openlocfilehash: 9e7c023ec371dd6695ffba3368502e5b593c4608
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57369534"
---
# <a name="how-to-create-an-expander-with-a-scrollviewer"></a><span data-ttu-id="985f1-102">如何：使用 ScrollViewer 创建 Expander</span><span class="sxs-lookup"><span data-stu-id="985f1-102">How to: Create an Expander with a ScrollViewer</span></span>
<span data-ttu-id="985f1-103">此示例演示如何创建<xref:System.Windows.Controls.Expander>包含复杂内容，例如图像和文本的控件。</span><span class="sxs-lookup"><span data-stu-id="985f1-103">This example shows how to create an <xref:System.Windows.Controls.Expander> control that contains complex content, such as an image and text.</span></span> <span data-ttu-id="985f1-104">该示例还包含的内容<xref:System.Windows.Controls.Expander>在<xref:System.Windows.Controls.ScrollViewer>控件。</span><span class="sxs-lookup"><span data-stu-id="985f1-104">The example also encloses the content of the <xref:System.Windows.Controls.Expander> in a <xref:System.Windows.Controls.ScrollViewer> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="985f1-105">示例</span><span class="sxs-lookup"><span data-stu-id="985f1-105">Example</span></span>  
 <span data-ttu-id="985f1-106">下面的示例演示如何创建<xref:System.Windows.Controls.Expander>。</span><span class="sxs-lookup"><span data-stu-id="985f1-106">The following example shows how to create an <xref:System.Windows.Controls.Expander>.</span></span> <span data-ttu-id="985f1-107">该示例使用<xref:System.Windows.Controls.Primitives.BulletDecorator>控件，它包含图像和文本，为了定义<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>。</span><span class="sxs-lookup"><span data-stu-id="985f1-107">The example uses a <xref:System.Windows.Controls.Primitives.BulletDecorator> control, which contains an image and text, in order to define the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A>.</span></span> <span data-ttu-id="985f1-108">一个<xref:System.Windows.Controls.ScrollViewer>控件提供了用于滚动扩展的内容的方法。</span><span class="sxs-lookup"><span data-stu-id="985f1-108">A <xref:System.Windows.Controls.ScrollViewer> control provides a method for scrolling the expanded content.</span></span>  
  
 <span data-ttu-id="985f1-109">请注意，该示例设置<xref:System.Windows.FrameworkElement.Height%2A>属性上的<xref:System.Windows.Controls.ScrollViewer>而不是对的内容。</span><span class="sxs-lookup"><span data-stu-id="985f1-109">Note that the example sets the <xref:System.Windows.FrameworkElement.Height%2A> property on the <xref:System.Windows.Controls.ScrollViewer> instead of on the content.</span></span> <span data-ttu-id="985f1-110">如果<xref:System.Windows.FrameworkElement.Height%2A>内容，设置<xref:System.Windows.Controls.ScrollViewer>不允许用户滚动内容。</span><span class="sxs-lookup"><span data-stu-id="985f1-110">If the <xref:System.Windows.FrameworkElement.Height%2A> is set on the content, the <xref:System.Windows.Controls.ScrollViewer> does not allow the user to scroll the content.</span></span> <span data-ttu-id="985f1-111"><xref:System.Windows.FrameworkElement.Width%2A>上设置属性<xref:System.Windows.Controls.Expander>控件，此设置适用于<xref:System.Windows.Controls.HeaderedContentControl.Header%2A>和扩展的内容。</span><span class="sxs-lookup"><span data-stu-id="985f1-111">The <xref:System.Windows.FrameworkElement.Width%2A> property is set on the <xref:System.Windows.Controls.Expander> control and this setting applies to the <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> and the expanded content.</span></span>  
  
 [!code-xaml[ExpanderRichContent#CreateExpander](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml#createexpander)]  
  
 [!code-csharp[ExpanderRichContent#CreateExpanderCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ExpanderRichContent/CSharp/Window1.xaml.cs#createexpandercode)]  
  
## <a name="see-also"></a><span data-ttu-id="985f1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="985f1-112">See also</span></span>
- <xref:System.Windows.Controls.Expander>
- [<span data-ttu-id="985f1-113">扩展器概述</span><span class="sxs-lookup"><span data-stu-id="985f1-113">Expander Overview</span></span>](expander-overview.md)
- [<span data-ttu-id="985f1-114">帮助主题</span><span class="sxs-lookup"><span data-stu-id="985f1-114">How-to Topics</span></span>](expander-how-to-topics.md)
