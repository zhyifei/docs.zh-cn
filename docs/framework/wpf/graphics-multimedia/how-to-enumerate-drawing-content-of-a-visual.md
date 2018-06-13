---
title: 如何：枚举 Visual 的绘图内容
ms.date: 03/30/2017
helpviewer_keywords:
- retrieving the DrawingGroup value of a Visual [WPF]
- enumerating the contents of a Visual [WPF]
ms.assetid: 2974ddb3-2997-4713-8fd2-e93d549c58a8
ms.openlocfilehash: 19c37ec7df3542eb46b182f4790059eb16fef90b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559397"
---
# <a name="how-to-enumerate-drawing-content-of-a-visual"></a><span data-ttu-id="eadde-102">如何：枚举 Visual 的绘图内容</span><span class="sxs-lookup"><span data-stu-id="eadde-102">How to: Enumerate Drawing Content of a Visual</span></span>
<span data-ttu-id="eadde-103"><xref:System.Windows.Media.Drawing>对象提供的对象模型，用于枚举的内容<xref:System.Windows.Media.Visual>。</span><span class="sxs-lookup"><span data-stu-id="eadde-103">The <xref:System.Windows.Media.Drawing> object provide an object model for enumerating the contents of a <xref:System.Windows.Media.Visual>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eadde-104">示例</span><span class="sxs-lookup"><span data-stu-id="eadde-104">Example</span></span>  
 <span data-ttu-id="eadde-105">下面的示例使用<xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>方法来检索<xref:System.Windows.Media.DrawingGroup>值<xref:System.Windows.Media.Visual>并枚举该值。</span><span class="sxs-lookup"><span data-stu-id="eadde-105">The following example uses the <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> method to retrieve the <xref:System.Windows.Media.DrawingGroup> value of a <xref:System.Windows.Media.Visual> and enumerate it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eadde-106">当你枚举视觉对象的内容时，就在检索<xref:System.Windows.Media.Drawing>对象，且不基础数据的表示形式呈现为向量图形指令列表。</span><span class="sxs-lookup"><span data-stu-id="eadde-106">When you are enumerating the contents of the visual, you are retrieving <xref:System.Windows.Media.Drawing> objects, and not the underlying representation of the render data as a vector graphics instruction list.</span></span> <span data-ttu-id="eadde-107">有关详细信息，请参阅 [WPF 图形呈现概述](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="eadde-107">For more information, see [WPF Graphics Rendering Overview](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md).</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMRetrieveDrawings](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/EnumerateDrawingsExample.xaml.cs#graphicsmmretrievedrawings)]  
  
## <a name="see-also"></a><span data-ttu-id="eadde-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="eadde-108">See Also</span></span>  
 <xref:System.Windows.Media.Drawing>  
 <xref:System.Windows.Media.DrawingGroup>  
 <xref:System.Windows.Media.VisualTreeHelper>  
 [<span data-ttu-id="eadde-109">Drawing 对象概述</span><span class="sxs-lookup"><span data-stu-id="eadde-109">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)  
 [<span data-ttu-id="eadde-110">WPF 图形呈现概述</span><span class="sxs-lookup"><span data-stu-id="eadde-110">WPF Graphics Rendering Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/wpf-graphics-rendering-overview.md)
