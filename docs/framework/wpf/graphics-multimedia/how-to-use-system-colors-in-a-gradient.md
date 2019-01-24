---
title: 如何：在渐变中使用系统颜色
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 44dfd30dc8d21e638855a383f1c9360a61ce81f9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54726411"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="9f932-102">如何：在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="9f932-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="9f932-103">若要在渐变中使用系统颜色，请使用 *\<SystemColor >* 颜色和 *\<SystemColor >* ColorKey 静态属性<xref:System.Windows.SystemColors>类来获取对颜色，引用其中 *\<SystemColor >* 是所需的系统颜色的名称。</span><span class="sxs-lookup"><span data-stu-id="9f932-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="9f932-104">使用 *\<SystemColor >* ColorKey 属性时想要创建的动态引用，随着系统主题变化而自动更新。</span><span class="sxs-lookup"><span data-stu-id="9f932-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="9f932-105">否则，请使用 *\<SystemColor >* Color 属性。</span><span class="sxs-lookup"><span data-stu-id="9f932-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f932-106">示例</span><span class="sxs-lookup"><span data-stu-id="9f932-106">Example</span></span>  
 <span data-ttu-id="9f932-107">以下示例使用动态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="9f932-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="9f932-108">下一个示例使用静态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="9f932-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="9f932-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f932-109">See also</span></span>
- <xref:System.Windows.SystemColors>
- [<span data-ttu-id="9f932-110">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="9f932-110">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [<span data-ttu-id="9f932-111">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="9f932-111">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
