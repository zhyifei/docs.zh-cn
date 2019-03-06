---
title: 如何：使用系统画笔绘制区域
ms.date: 03/30/2017
helpviewer_keywords:
- system brushes [WPF], painting with
- painting [WPF], with system brushes
- brushes [WPF], painting with system brushes [WPF]
ms.assetid: 5141a763-9235-42cb-a6bb-afc75513eac7
ms.openlocfilehash: 7beaf4370f115a3995c9ca23bb0022bd5b269193
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364107"
---
# <a name="how-to-paint-an-area-with-a-system-brush"></a><span data-ttu-id="1ee7b-102">如何：使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="1ee7b-102">How to: Paint an Area with a System Brush</span></span>
<span data-ttu-id="1ee7b-103"><xref:System.Windows.SystemColors>类提供了访问系统画笔和颜色，如<xref:System.Windows.SystemColors.ControlBrush%2A>， <xref:System.Windows.SystemColors.ControlBrushKey%2A>，和<xref:System.Windows.SystemColors.DesktopBrush%2A>。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-103">The <xref:System.Windows.SystemColors> class provides access to system brushes and colors, such as <xref:System.Windows.SystemColors.ControlBrush%2A>, <xref:System.Windows.SystemColors.ControlBrushKey%2A>, and <xref:System.Windows.SystemColors.DesktopBrush%2A>.</span></span> <span data-ttu-id="1ee7b-104">系统画笔是<xref:System.Windows.Media.SolidColorBrush>对象，它使用指定的系统颜色绘制区域。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-104">A system brush is a <xref:System.Windows.Media.SolidColorBrush> object that paints an area with the specified system color.</span></span> <span data-ttu-id="1ee7b-105">系统画笔总是生成纯色填充，它不能用于创建渐变。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-105">A system brush always produces a solid fill; it can't be used to create a gradient.</span></span>  
  
 <span data-ttu-id="1ee7b-106">可以将系统画笔用作静态资源，也可以用作动态资源。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-106">You can use system brushes as either a static or a dynamic resource.</span></span> <span data-ttu-id="1ee7b-107">如果希望在应用程序运行期间画笔自动进行更新（当用户更改系统画笔时），请使用动态资源；否则请使用静态资源。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-107">Use a dynamic resource if you want the brush to update automatically if the user changes the system brush as the application is running; otherwise, use a static resource.</span></span> <span data-ttu-id="1ee7b-108">SystemColors 类包含大量静态属性，这些属性严格遵循命名约定：</span><span class="sxs-lookup"><span data-stu-id="1ee7b-108">The SystemColors class contains a variety of static properties that follow a strict naming convention:</span></span>  
  
-   <span data-ttu-id="1ee7b-109">*\<SystemColor>* Brush</span><span class="sxs-lookup"><span data-stu-id="1ee7b-109">*\<SystemColor>* Brush</span></span>  
  
     <span data-ttu-id="1ee7b-110">获取对的静态引用<xref:System.Windows.Media.SolidColorBrush>指定的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-110">Gets a static reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="1ee7b-111">*\<SystemColor>* BrushKey</span><span class="sxs-lookup"><span data-stu-id="1ee7b-111">*\<SystemColor>* BrushKey</span></span>  
  
     <span data-ttu-id="1ee7b-112">获取到的动态引用<xref:System.Windows.Media.SolidColorBrush>指定的系统颜色。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-112">Gets a dynamic reference to a <xref:System.Windows.Media.SolidColorBrush> of the specified system color.</span></span>  
  
-   <span data-ttu-id="1ee7b-113">*\<SystemColor>* Color</span><span class="sxs-lookup"><span data-stu-id="1ee7b-113">*\<SystemColor>* Color</span></span>  
  
     <span data-ttu-id="1ee7b-114">获取对的静态引用<xref:System.Windows.Media.Color>指定的系统颜色的结构。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-114">Gets a static reference to a <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
-   <span data-ttu-id="1ee7b-115">*\<SystemColor>* ColorKey</span><span class="sxs-lookup"><span data-stu-id="1ee7b-115">*\<SystemColor>* ColorKey</span></span>  
  
     <span data-ttu-id="1ee7b-116">获取到的动态引用<xref:System.Windows.Media.Color>指定的系统颜色的结构。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-116">Gets a dynamic reference to the <xref:System.Windows.Media.Color> structure of the specified system color.</span></span>  
  
 <span data-ttu-id="1ee7b-117">系统颜色是<xref:System.Windows.Media.Color>结构，它可用于配置画笔。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-117">A system color is a <xref:System.Windows.Media.Color> structure that can be used to configure a brush.</span></span> <span data-ttu-id="1ee7b-118">例如，可以创建通过设置使用系统颜色的渐变<xref:System.Windows.Media.GradientStop.Color%2A>的属性<xref:System.Windows.Media.LinearGradientBrush>对象的使用系统颜色的渐变停止点。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-118">For example, you can create a gradient using system colors by setting the <xref:System.Windows.Media.GradientStop.Color%2A> properties of a <xref:System.Windows.Media.LinearGradientBrush> object's gradient stops with system colors.</span></span> <span data-ttu-id="1ee7b-119">有关示例，请参阅[渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-119">For an example, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ee7b-120">示例</span><span class="sxs-lookup"><span data-stu-id="1ee7b-120">Example</span></span>  
 <span data-ttu-id="1ee7b-121">以下示例使用动态系统画笔引用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-121">The following example uses a dynamic system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMDynamicSystemColorDesktopBrushKeyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/DynamicSystemBrushExample.xaml#graphicsmmdynamicsystemcolordesktopbrushkeyexamplewholepage)]  
  
 <span data-ttu-id="1ee7b-122">下一个示例使用静态系统画笔引用来设置按钮的背景。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-122">The next example uses a static system brush reference to set the Background of a button.</span></span>  
  
 [!code-xaml[brushsamples_snip#GraphicsMMStaticSystemColorDesktopBrushExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/StaticSystemBrushExample.xaml#graphicsmmstaticsystemcolordesktopbrushexamplewholepage)]  
  
 <span data-ttu-id="1ee7b-123">有关演示如何在渐变中使用系统颜色的示例，请参阅[渐变中使用系统颜色](how-to-use-system-colors-in-a-gradient.md)。</span><span class="sxs-lookup"><span data-stu-id="1ee7b-123">For an example showing how to use a system color in a gradient, see [Use System Colors in a Gradient](how-to-use-system-colors-in-a-gradient.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ee7b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ee7b-124">See also</span></span>
- [<span data-ttu-id="1ee7b-125">在渐变中使用系统颜色</span><span class="sxs-lookup"><span data-stu-id="1ee7b-125">Use System Colors in a Gradient</span></span>](how-to-use-system-colors-in-a-gradient.md)
- [<span data-ttu-id="1ee7b-126">使用纯色和渐变进行绘制概述</span><span class="sxs-lookup"><span data-stu-id="1ee7b-126">Painting with Solid Colors and Gradients Overview</span></span>](painting-with-solid-colors-and-gradients-overview.md)
