---
title: 如何：向 Viewbox 的内容应用 Stretch 属性
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- StretchDirection properties [WPF]
- Stretch properties [WPF]
- controls [WPF], Viewbox
- Viewbox control [WPF]
ms.assetid: b9c22ef4-bce4-4300-9e0c-8260b7db83cc
ms.openlocfilehash: 3e81ec9fd045bb3fcf359943e455d2cce94aec55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552800"
---
# <a name="how-to-apply-stretch-properties-to-the-contents-of-a-viewbox"></a><span data-ttu-id="6ac3f-102">如何：向 Viewbox 的内容应用 Stretch 属性</span><span class="sxs-lookup"><span data-stu-id="6ac3f-102">How to: Apply Stretch Properties to the Contents of a Viewbox</span></span>
## <a name="example"></a><span data-ttu-id="6ac3f-103">示例</span><span class="sxs-lookup"><span data-stu-id="6ac3f-103">Example</span></span>  
 <span data-ttu-id="6ac3f-104">此示例演示如何更改的值<xref:System.Windows.Controls.Viewbox.StretchDirection%2A>和<xref:System.Windows.Controls.Viewbox.Stretch%2A>属性<xref:System.Windows.Controls.Viewbox>。</span><span class="sxs-lookup"><span data-stu-id="6ac3f-104">This example shows how to change the value of the <xref:System.Windows.Controls.Viewbox.StretchDirection%2A> and <xref:System.Windows.Controls.Viewbox.Stretch%2A> properties of a <xref:System.Windows.Controls.Viewbox>.</span></span>  
  
 <span data-ttu-id="6ac3f-105">第一个示例使用[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]定义<xref:System.Windows.Controls.Viewbox>元素。</span><span class="sxs-lookup"><span data-stu-id="6ac3f-105">The first example uses [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] to define a <xref:System.Windows.Controls.Viewbox> element.</span></span> <span data-ttu-id="6ac3f-106">它将分配<xref:System.Windows.FrameworkElement.MaxWidth%2A>和<xref:System.Windows.FrameworkElement.MaxHeight%2A>的 400。</span><span class="sxs-lookup"><span data-stu-id="6ac3f-106">It assigns a <xref:System.Windows.FrameworkElement.MaxWidth%2A> and <xref:System.Windows.FrameworkElement.MaxHeight%2A> of 400.</span></span> <span data-ttu-id="6ac3f-107">示例嵌套<xref:System.Windows.Controls.Image>中的元素<xref:System.Windows.Controls.Viewbox>。</span><span class="sxs-lookup"><span data-stu-id="6ac3f-107">The example nests an <xref:System.Windows.Controls.Image> element within the <xref:System.Windows.Controls.Viewbox>.</span></span> <span data-ttu-id="6ac3f-108"><xref:System.Windows.Controls.Button> 对应的属性值的元素<xref:System.Windows.Controls.Viewbox.Stretch%2A>和<xref:System.Windows.Controls.StretchDirection>枚举操作的嵌套的拉伸行为<xref:System.Windows.Controls.Image>。</span><span class="sxs-lookup"><span data-stu-id="6ac3f-108"><xref:System.Windows.Controls.Button> elements that correspond to the property values for the <xref:System.Windows.Controls.Viewbox.Stretch%2A> and <xref:System.Windows.Controls.StretchDirection> enumerations manipulate the stretching behavior of the nested <xref:System.Windows.Controls.Image>.</span></span>  
  
 [!code-xaml[viewboxStretchLayoutSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="6ac3f-109">下面的代码隐藏文件句柄<xref:System.Windows.Controls.Button><xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件的上一个[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例定义。</span><span class="sxs-lookup"><span data-stu-id="6ac3f-109">The following code-behind file handles the <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.Primitives.ButtonBase.Click> events that the previous [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example defines.</span></span>  
  
 [!code-csharp[viewboxStretchLayoutSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/viewboxStretchLayoutSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[viewboxStretchLayoutSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/viewboxStretchLayoutSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="6ac3f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ac3f-110">See Also</span></span>  
 <xref:System.Windows.Controls.Viewbox>  
 <xref:System.Windows.Media.Stretch>  
 <xref:System.Windows.Controls.StretchDirection>
