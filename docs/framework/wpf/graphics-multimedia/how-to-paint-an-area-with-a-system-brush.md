---
title: "如何：使用系统画笔绘制区域"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 87979c16d52262c665e2fb37fdf6d7550c5930c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="92af5-102">如何：使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="92af5-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="92af5-103"><xref:System.Windows.SystemColors>类提供了访问系统画笔和颜色，如<xref:System.Windows.SystemColors.ControlBrush%2A>， <xref:System.Windows.SystemColors.ControlBrushKey%2A>，和<xref:System.Windows.SystemColors.DesktopBrush%2A>。</span><span class="sxs-lookup"><span data-stu-id="92af5-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="92af5-104">系统画笔是<xref:System.Windows.Media.SolidColorBrush>使用指定的系统颜色绘制区域的对象。</span><span class="sxs-lookup"><span data-stu-id="92af5-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="92af5-105">系统画笔总是生成纯色填充，它不能用于创建渐变。</span><span class="sxs-lookup"><span data-stu-id="92af5-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="92af5-106">可以将系统画笔用作静态资源，也可以用作动态资源。</span><span class="sxs-lookup"><span data-stu-id="92af5-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="92af5-107">如果希望在应用程序运行期间画笔自动进行更新（当用户更改系统画笔时），请使用动态资源；否则请使用静态资源。</span><span class="sxs-lookup"><span data-stu-id="92af5-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="92af5-108">SystemColors 类包含大量静态属性，这些属性严格遵循命名约定：</span><span class="sxs-lookup"><span data-stu-id="92af5-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="92af5-109">*\<SystemColor>*Brush</span><span class="sxs-lookup"><span data-stu-id="92af5-109">*\<SystemColor>*Brush</span></span>  
  
     <span data-ttu-id="92af5-110">获取的静态引用<xref:System.Windows.Media.SolidColorBrush>的指定的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="92af5-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="92af5-111">*\<SystemColor>*BrushKey</span><span class="sxs-lookup"><span data-stu-id="92af5-111">*\<SystemColor>*BrushKey</span></span>  
  
     <span data-ttu-id="92af5-112">获取对动态引用<xref:System.Windows.Media.SolidColorBrush>的指定的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="92af5-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="92af5-113">*\<SystemColor>*Color</span><span class="sxs-lookup"><span data-stu-id="92af5-113">*\<SystemColor>*Color</span></span>  
  
     <span data-ttu-id="92af5-114">获取的静态引用<xref:System.Windows.Media.Color>结构指定的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="92af5-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="92af5-115">*\<SystemColor>*ColorKey</span><span class="sxs-lookup"><span data-stu-id="92af5-115">*\<SystemColor>*ColorKey</span></span>  
  
     <span data-ttu-id="92af5-116">获取对动态引用<xref:System.Windows.Media.Color>结构指定的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="92af5-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="92af5-117">系统颜色是<xref:System.Windows.Media.Color>结构，它可以用于配置画笔。</span><span class="sxs-lookup"><span data-stu-id="92af5-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="92af5-118">例如，你可以创建使用系统颜色设置的渐变<xref:System.Windows.Media.GradientStop.Color%2A>属性<xref:System.Windows.Media.LinearGradientBrush>对象的系统颜色渐变停止点。</span><span class="sxs-lookup"><span data-stu-id="92af5-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="92af5-119">有关示例，请参阅[渐变中的使用系统颜色](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)。</span><span class="sxs-lookup"><span data-stu-id="92af5-119">For an example, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="92af5-120">示例</span><span class="sxs-lookup"><span data-stu-id="92af5-120">Example</span></span>  
 <span data-ttu-id="92af5-121">以下示例使用动态系统画笔引用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="92af5-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="92af5-122">下一个示例使用静态系统画笔引用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="92af5-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="92af5-123">有关演示如何使用系统颜色渐变中的示例，请参阅[渐变中使用系统颜色](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)。</span><span class="sxs-lookup"><span data-stu-id="92af5-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92af5-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="92af5-124">See Also</span></span>  
 [<span data-ttu-id="92af5-125">在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="92af5-125">Use System Colors in a Gradient</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-use-system-colors-in-a-gradient.md)  
 [<span data-ttu-id="92af5-126">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="92af5-126">Painting with Solid Colors and Gradients Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/painting-with-solid-colors-and-gradients-overview.md)
