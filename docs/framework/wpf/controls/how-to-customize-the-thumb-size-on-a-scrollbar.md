---
title: 如何：自定义滚动条上的滚动块大小
ms.date: 03/30/2017
helpviewer_keywords:
- ScrollBar control [WPF]
- customizing thumb size [WPF]
- thumb size [WPF]
ms.assetid: fa32b866-5ca1-4e73-85e7-2ac64b80d194
ms.openlocfilehash: 2c77eb23c1a42051a7c2d81f3454eb51425fa034
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54590859"
---
# <a name="how-to-customize-the-thumb-size-on-a-scrollbar"></a><span data-ttu-id="1660f-102">如何：自定义滚动条上的滚动块大小</span><span class="sxs-lookup"><span data-stu-id="1660f-102">How to: Customize the Thumb Size on a ScrollBar</span></span>
<span data-ttu-id="1660f-103">本主题介绍如何设置<xref:System.Windows.Controls.Primitives.Thumb>的<xref:System.Windows.Controls.Primitives.ScrollBar>固定的大小以及如何指定的最小大小<xref:System.Windows.Controls.Primitives.Thumb>的<xref:System.Windows.Controls.Primitives.ScrollBar>。</span><span class="sxs-lookup"><span data-stu-id="1660f-103">This topic explains how to set the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar> to a fixed size and how to specify a minimum size for the <xref:System.Windows.Controls.Primitives.Thumb> of a <xref:System.Windows.Controls.Primitives.ScrollBar>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1660f-104">示例</span><span class="sxs-lookup"><span data-stu-id="1660f-104">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="1660f-105">描述</span><span class="sxs-lookup"><span data-stu-id="1660f-105">Description</span></span>  
 <span data-ttu-id="1660f-106">下面的示例创建<xref:System.Windows.Controls.Primitives.ScrollBar>具有<xref:System.Windows.Controls.Primitives.Thumb>具有固定大小。</span><span class="sxs-lookup"><span data-stu-id="1660f-106">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a fixed size.</span></span> <span data-ttu-id="1660f-107">该示例设置<xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A>的属性<xref:System.Windows.Controls.Primitives.Thumb>到<xref:System.Double.NaN>设置的高度和<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="1660f-107">The example sets the <xref:System.Windows.Controls.Primitives.Track.ViewportSize%2A> property of the <xref:System.Windows.Controls.Primitives.Thumb> to <xref:System.Double.NaN> and sets the height of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  <span data-ttu-id="1660f-108">若要创建水平<xref:System.Windows.Controls.Primitives.ScrollBar>与<xref:System.Windows.Controls.Primitives.Thumb>具有固定的宽度，则设置的宽度<xref:System.Windows.Controls.Primitives.Thumb>。</span><span class="sxs-lookup"><span data-stu-id="1660f-108">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a fixed width, set the width of the <xref:System.Windows.Controls.Primitives.Thumb>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="1660f-109">代码</span><span class="sxs-lookup"><span data-stu-id="1660f-109">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#1)]  
  
## <a name="description"></a><span data-ttu-id="1660f-110">描述</span><span class="sxs-lookup"><span data-stu-id="1660f-110">Description</span></span>  
 <span data-ttu-id="1660f-111">下面的示例创建<xref:System.Windows.Controls.Primitives.ScrollBar>具有<xref:System.Windows.Controls.Primitives.Thumb>与最小大小。</span><span class="sxs-lookup"><span data-stu-id="1660f-111">The following example creates a <xref:System.Windows.Controls.Primitives.ScrollBar> that has a <xref:System.Windows.Controls.Primitives.Thumb> with a minimum size.</span></span> <span data-ttu-id="1660f-112">该示例设置的值<xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="1660f-112">The example sets the value of <xref:System.Windows.SystemParameters.VerticalScrollBarButtonHeightKey%2A>.</span></span> <span data-ttu-id="1660f-113">若要创建水平<xref:System.Windows.Controls.Primitives.ScrollBar>与<xref:System.Windows.Controls.Primitives.Thumb>的最小宽度，设置<xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="1660f-113">To create a horizontal <xref:System.Windows.Controls.Primitives.ScrollBar> with a <xref:System.Windows.Controls.Primitives.Thumb> that has a minimum width, set the <xref:System.Windows.SystemParameters.HorizontalScrollBarButtonWidthKey%2A>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="1660f-114">代码</span><span class="sxs-lookup"><span data-stu-id="1660f-114">Code</span></span>  
 [!code-xaml[ScrollBarCustomThumbSize#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ScrollBarCustomThumbSize/CS/Window1.xaml#2)]  
  
## <a name="see-also"></a><span data-ttu-id="1660f-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1660f-115">See also</span></span>
- [<span data-ttu-id="1660f-116">ScrollBar 样式和模板</span><span class="sxs-lookup"><span data-stu-id="1660f-116">ScrollBar Styles and Templates</span></span>](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md)
