---
title: "如何：使用 SystemFonts"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- system fonts [WPF]
- fonts [WPF], system fonts
- classes [WPF], SystemFonts
ms.assetid: 3f46a4ec-2225-408a-8123-8838a8f7057a
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8ce82724a4e9a547b8441628f43621f29eab6307
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-systemfonts"></a><span data-ttu-id="3f2b5-102">如何：使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="3f2b5-102">How to: Use SystemFonts</span></span>
<span data-ttu-id="3f2b5-103">此示例演示如何使用的静态资源<xref:System.Windows.SystemFonts>才能样式或自定义按钮的类。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-103">This example shows how to use the static resources of the <xref:System.Windows.SystemFonts> class in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3f2b5-104">示例</span><span class="sxs-lookup"><span data-stu-id="3f2b5-104">Example</span></span>  
 <span data-ttu-id="3f2b5-105">系统资源将系统确定的许多值以资源和属性的形式公开，以帮助创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-105">System resources expose several system-determined values as both resources and properties in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="3f2b5-106"><xref:System.Windows.SystemFonts>是一个类，其中包含这两个系统字体值作为静态属性和引用可以用于在运行时动态访问这些值的资源键的属性。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-106"><xref:System.Windows.SystemFonts> is a class that contains both system font values as static properties, and properties that reference resource keys that can be used to access those values dynamically at run time.</span></span> <span data-ttu-id="3f2b5-107">例如，<xref:System.Windows.SystemFonts.CaptionFontFamily%2A>是<xref:System.Windows.SystemFonts>值，和<xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>是相应的资源键。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-107">For example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> is a <xref:System.Windows.SystemFonts> value, and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A> is a corresponding resource key.</span></span>  
  
 <span data-ttu-id="3f2b5-108">在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你可以使用的成员<xref:System.Windows.SystemFonts>作为静态属性或 （具有作为键的静态属性值） 的动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemFonts> as either static properties or dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="3f2b5-109">如果希望字体规格在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态值引用。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-109">Use a dynamic resource reference if you want the font metric to automatically update while the application runs; otherwise, use a static value reference.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f2b5-110">资源键属性名称后面附有“Key”后缀。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-110">The resource keys have the suffix "Key" appended to the property name.</span></span>  
  
 <span data-ttu-id="3f2b5-111">下面的示例演示如何访问和使用的属性<xref:System.Windows.SystemFonts>作为才能样式或自定义按钮的静态值。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-111">The following example shows how to access and use the properties of <xref:System.Windows.SystemFonts> as static values in order to style or customize a button.</span></span> <span data-ttu-id="3f2b5-112">此标记的示例将分配<xref:System.Windows.SystemFonts>至一个按钮的值。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-112">This markup example assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#FontStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#fontstaticresources)]  
  
 <span data-ttu-id="3f2b5-113">若要使用的值<xref:System.Windows.SystemFonts>不需要在代码中，使用静态值或动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-113">To use the values of <xref:System.Windows.SystemFonts> in code, you do not have to use either a static value or a dynamic resource reference.</span></span> <span data-ttu-id="3f2b5-114">相反，使用的非键属性<xref:System.Windows.SystemFonts>类。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-114">Instead, use the non-key properties of the <xref:System.Windows.SystemFonts> class.</span></span> <span data-ttu-id="3f2b5-115">虽然非键属性已明确定义为静态属性的运行时行为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]承载的系统将重新计算实时的属性，并将正确考虑对系统值面向用户的更改。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-115">Although the non-key properties are apparently defined as static properties, the run-time behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in real time and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="3f2b5-116">以下示例演示如何指定按钮的字体设置。</span><span class="sxs-lookup"><span data-stu-id="3f2b5-116">The following example shows how to specify the font settings of a button.</span></span>  
  
 [!code-csharp[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#fontresourcescode)]
 [!code-vb[SystemRes_snip#FontResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#fontresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="3f2b5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3f2b5-117">See Also</span></span>  
 <xref:System.Windows.SystemFonts>  
 [<span data-ttu-id="3f2b5-118">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="3f2b5-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="3f2b5-119">使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="3f2b5-119">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="3f2b5-120">使用系统字体键</span><span class="sxs-lookup"><span data-stu-id="3f2b5-120">Use System Fonts Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-fonts-keys.md)  
 [<span data-ttu-id="3f2b5-121">操作说明主题</span><span class="sxs-lookup"><span data-stu-id="3f2b5-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)  
 [<span data-ttu-id="3f2b5-122">x:Static 标记扩展</span><span class="sxs-lookup"><span data-stu-id="3f2b5-122">x:Static Markup Extension</span></span>](../../../../docs/framework/xaml-services/x-static-markup-extension.md)  
 [<span data-ttu-id="3f2b5-123">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="3f2b5-123">XAML Resources</span></span>](../../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="3f2b5-124">DynamicResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="3f2b5-124">DynamicResource Markup Extension</span></span>](../../../../docs/framework/wpf/advanced/dynamicresource-markup-extension.md)
