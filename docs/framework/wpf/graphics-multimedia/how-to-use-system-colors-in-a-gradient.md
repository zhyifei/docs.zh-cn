---
title: "如何：在渐变中使用系统颜色"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- gradients [WPF], system colors in
- system colors in gradients [WPF]
ms.assetid: 11942e7e-6300-4b50-8ed1-f50e8d20e7d2
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 105e22588f68d999811f5482342d53851a4d25eb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-colors-in-a-gradient"></a><span data-ttu-id="ba9aa-102">如何：在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="ba9aa-102">How to: Use System Colors in a Gradient</span></span>
<span data-ttu-id="ba9aa-103">若要在渐变中使用系统颜色，请使用 *\<SystemColor >*颜色和 *\<SystemColor >*ColorKey 的静态属性的<xref:System.Windows.SystemColors>类来获取对颜色，引用其中 *\<SystemColor >*是所需的系统颜色的名称。</span><span class="sxs-lookup"><span data-stu-id="ba9aa-103">To use a system color in a gradient, you use the *\<SystemColor>*Color and *\<SystemColor>*ColorKey static properties of the <xref:System.Windows.SystemColors> class to obtain a reference to the color, where *\<SystemColor>* is the name of the desired system color.</span></span> <span data-ttu-id="ba9aa-104">使用 *\<SystemColor >*ColorKey 属性时你想要创建的动态引用，随着系统主题更改而自动更新。</span><span class="sxs-lookup"><span data-stu-id="ba9aa-104">Use the *\<SystemColor>*ColorKey properties when you want to create a dynamic reference that updates automatically as the system theme changes.</span></span> <span data-ttu-id="ba9aa-105">否则，请使用 *\<SystemColor >*颜色属性。</span><span class="sxs-lookup"><span data-stu-id="ba9aa-105">Otherwise, use the *\<SystemColor>*Color properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba9aa-106">示例</span><span class="sxs-lookup"><span data-stu-id="ba9aa-106">Example</span></span>  
 <span data-ttu-id="ba9aa-107">以下示例使用动态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="ba9aa-107">The following example uses dynamic system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemColorExample.xaml#graphicsmmdynamicsystemcolorgradientexamplewholepage)]  
  
 <span data-ttu-id="ba9aa-108">下一个示例使用静态系统颜色资源创建渐变。</span><span class="sxs-lookup"><span data-stu-id="ba9aa-108">The next example uses static system color resources to create a gradient.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorGradientExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemColorExample.xaml#graphicsmmstaticsystemcolorgradientexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="ba9aa-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba9aa-109">See Also</span></span>  
 <xref:System.Windows.SystemColors>  
 [<span data-ttu-id="ba9aa-110">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="ba9aa-110">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="ba9aa-111">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="ba9aa-111">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
