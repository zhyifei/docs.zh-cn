---
title: 如何：在渐变中使用系统颜色
ms.date: 03/30/2017
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
ms.openlocfilehash: 4c3fca1db031b0dc397e9db58195b9714ff8aa9a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33562175"
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="c53a8-102">如何：在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="c53a8-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="c53a8-103">若要在渐变中使用系统颜色，请使用 *\<SystemColor >* 颜色和 *\<SystemColor >* ColorKey 的静态属性的<xref:System.Windows.SystemColors>类来获取对颜色，引用其中 *\<SystemColor >* 是所需的系统颜色的名称。</span><span class="sxs-lookup"><span data-stu-id="c53a8-103">To use a system color in a gradient, you use the *\<SystemColor>* Color and *\<SystemColor>* ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="c53a8-104">使用 *\<SystemColor >* ColorKey 属性时你想要创建的动态引用，随着系统主题更改而自动更新。</span><span class="sxs-lookup"><span data-stu-id="c53a8-104">Use the *\<SystemColor>* ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="c53a8-105">否则，请使用 *\<SystemColor >* 颜色属性。</span><span class="sxs-lookup"><span data-stu-id="c53a8-105">Otherwise, use the *\<SystemColor>* Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c53a8-106">示例</span><span class="sxs-lookup"><span data-stu-id="c53a8-106">Example</span></span>  
 <span data-ttu-id="c53a8-107">以下示例使用动态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="c53a8-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="c53a8-108">下一个示例使用静态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="c53a8-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="c53a8-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="c53a8-109">See Also</span></span>  
 <xref:System.Windows.SystemColors>  
 [<span data-ttu-id="c53a8-110">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="c53a8-110">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="c53a8-111">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="c53a8-111">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
