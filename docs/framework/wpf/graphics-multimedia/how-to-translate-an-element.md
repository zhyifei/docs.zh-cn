---
title: "如何：平移元素"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 222aebe0ffe3d2bb1d84002a2ad94b0b92ede15b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="8b7cd-102">如何：平移元素</span><span class="sxs-lookup"><span data-stu-id="8b7cd-102">How to: Translate an Element</span></span>
<span data-ttu-id="8b7cd-103">此示例说明了如何平移 （移动） 元素使用<xref:System.Windows.Media.TranslateTransform>。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="8b7cd-104"><xref:System.Windows.Media.TranslateTransform>类非常适合移动的面板内的不支持绝对定位的元素。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="8b7cd-105">例如，通过应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>的元素的属性，可以移动中的某个元素<xref:System.Windows.Controls.StackPanel>或<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="8b7cd-106">使用<xref:System.Windows.Media.TranslateTransform.X%2A>属性<xref:System.Windows.Media.TranslateTransform>指定量，以像素为单位，将沿 x 轴的元素。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="8b7cd-107">使用<xref:System.Windows.Media.TranslateTransform.Y%2A>属性指定量，以像素为单位，将沿 y 轴的元素。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="8b7cd-108">最后，应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="8b7cd-109">下面的示例使用<xref:System.Windows.Media.TranslateTransform>到右部和 50 像素向下移动元素 50 像素。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b7cd-110">示例</span><span class="sxs-lookup"><span data-stu-id="8b7cd-110">Example</span></span>  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="8b7cd-111">有关完整示例，请参阅 [2D 转换示例](http://go.microsoft.com/fwlink/?LinkID=158252)。</span><span class="sxs-lookup"><span data-stu-id="8b7cd-111">For the complete sample, see [2-D Transforms Sample](http://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b7cd-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b7cd-112">See Also</span></span>  
 [<span data-ttu-id="8b7cd-113">转换概述</span><span class="sxs-lookup"><span data-stu-id="8b7cd-113">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
