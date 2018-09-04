---
title: 如何：平移元素
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], translations
ms.assetid: 461c8273-15df-42f6-8672-89ba22887cc0
ms.openlocfilehash: 04e1e8288bcccc4a310f05abff01fbdf160cdb11
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43505903"
---
# <a name="how-to-translate-an-element"></a><span data-ttu-id="f7e31-102">如何：平移元素</span><span class="sxs-lookup"><span data-stu-id="f7e31-102">How to: Translate an Element</span></span>
<span data-ttu-id="f7e31-103">以下示例显示如何平移 （移动） 元素来使用<xref:System.Windows.Media.TranslateTransform>。</span><span class="sxs-lookup"><span data-stu-id="f7e31-103">This example shows how to translate (move) an element by using a <xref:System.Windows.Media.TranslateTransform>.</span></span>  
  
 <span data-ttu-id="f7e31-104"><xref:System.Windows.Media.TranslateTransform>类是对于不支持绝对定位的面板内移动元素特别有用。</span><span class="sxs-lookup"><span data-stu-id="f7e31-104">The <xref:System.Windows.Media.TranslateTransform> class is especially useful for moving elements inside panels that do not support absolute positioning.</span></span> <span data-ttu-id="f7e31-105">例如，通过应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性，可以移动中的某个元素<xref:System.Windows.Controls.StackPanel>或<xref:System.Windows.Controls.DockPanel>。</span><span class="sxs-lookup"><span data-stu-id="f7e31-105">For example, by applying a <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of an element, you can move an element within a <xref:System.Windows.Controls.StackPanel> or <xref:System.Windows.Controls.DockPanel>.</span></span>  
  
 <span data-ttu-id="f7e31-106">使用<xref:System.Windows.Media.TranslateTransform.X%2A>属性的<xref:System.Windows.Media.TranslateTransform>指定量，以像素为单位，若要沿 x 轴移动元素。</span><span class="sxs-lookup"><span data-stu-id="f7e31-106">Use the <xref:System.Windows.Media.TranslateTransform.X%2A> property of the <xref:System.Windows.Media.TranslateTransform> to specify the amount, in pixels, to move the element along the x-axis.</span></span> <span data-ttu-id="f7e31-107">使用<xref:System.Windows.Media.TranslateTransform.Y%2A>属性来指定量，以像素为单位，若要沿 y 轴移动元素。</span><span class="sxs-lookup"><span data-stu-id="f7e31-107">Use the <xref:System.Windows.Media.TranslateTransform.Y%2A> property to specify the amount, in pixels, to move the element along the y-axis.</span></span> <span data-ttu-id="f7e31-108">最后，将应用<xref:System.Windows.Media.TranslateTransform>到<xref:System.Windows.UIElement.RenderTransform%2A>元素的属性。</span><span class="sxs-lookup"><span data-stu-id="f7e31-108">Finally, apply the <xref:System.Windows.Media.TranslateTransform> to the <xref:System.Windows.UIElement.RenderTransform%2A> property of the element.</span></span>  
  
 <span data-ttu-id="f7e31-109">下面的示例使用<xref:System.Windows.Media.TranslateTransform>可以向下移动到右和 50 个像素的元素 50 像素。</span><span class="sxs-lookup"><span data-stu-id="f7e31-109">The following example uses a <xref:System.Windows.Media.TranslateTransform> to move an element 50 pixels to the right and 50 pixels down.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7e31-110">示例</span><span class="sxs-lookup"><span data-stu-id="f7e31-110">Example</span></span>  
 [!code-xaml[transformsSample#53](../../../../samples/snippets/csharp/VS_Snippets_Wpf/transformsSample/CS/TranslateTransformExample.xaml#53)]  
  
 <span data-ttu-id="f7e31-111">有关完整示例，请参阅 [2D 转换示例](https://go.microsoft.com/fwlink/?LinkID=158252)。</span><span class="sxs-lookup"><span data-stu-id="f7e31-111">For the complete sample, see [2-D Transforms Sample](https://go.microsoft.com/fwlink/?LinkID=158252).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e31-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7e31-112">See Also</span></span>  
 [<span data-ttu-id="f7e31-113">转换概述</span><span class="sxs-lookup"><span data-stu-id="f7e31-113">Transforms Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/transforms-overview.md)
