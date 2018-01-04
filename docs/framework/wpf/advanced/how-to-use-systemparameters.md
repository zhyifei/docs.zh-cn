---
title: "如何：使用 SystemParameters"
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
helpviewer_keywords: classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
caps.latest.revision: "24"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec333fbc30374ff6f8e2e7674ab332644ff7aad0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-systemparameters"></a><span data-ttu-id="d0878-102">如何：使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="d0878-102">How to: Use SystemParameters</span></span>
<span data-ttu-id="d0878-103">此示例演示如何访问和使用的属性<xref:System.Windows.SystemParameters>才能样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="d0878-103">This example shows how to access and use the properties of <xref:System.Windows.SystemParameters> in order to style or customize a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0878-104">示例</span><span class="sxs-lookup"><span data-stu-id="d0878-104">Example</span></span>  
 <span data-ttu-id="d0878-105">系统资源将多个基于系统的设置以资源的形式公开，以帮助创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="d0878-105">System resources expose several system based settings as resources in order to help you create visuals that are consistent with system settings.</span></span> <span data-ttu-id="d0878-106"><xref:System.Windows.SystemParameters>是一个类，包含系统参数值属性，并将绑定到值的资源键。</span><span class="sxs-lookup"><span data-stu-id="d0878-106"><xref:System.Windows.SystemParameters> is a class that contains both system parameter value properties, and resource keys that bind to the values.</span></span> <span data-ttu-id="d0878-107">例如，<xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A>是<xref:System.Windows.SystemParameters>属性值和<xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>是相应的资源键。</span><span class="sxs-lookup"><span data-stu-id="d0878-107">For example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> is a <xref:System.Windows.SystemParameters> property value and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> is the corresponding resource key.</span></span>  
  
 <span data-ttu-id="d0878-108">在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]，你可以使用的成员<xref:System.Windows.SystemParameters>为静态属性用法或 （具有作为键的静态属性值） 的动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="d0878-108">In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], you can use the members of <xref:System.Windows.SystemParameters> as either a static property usage, or a dynamic resource references (with the static property value as the key).</span></span> <span data-ttu-id="d0878-109">如果希望基于系统的值在应用程序运行时自动更新，请使用动态资源引用；否则，请使用静态引用。</span><span class="sxs-lookup"><span data-stu-id="d0878-109">Use a dynamic resource reference if you want the system based value to update automatically while the application runs; otherwise, use a static reference.</span></span> <span data-ttu-id="d0878-110">资源键具有后缀`Key`追加到属性名称。</span><span class="sxs-lookup"><span data-stu-id="d0878-110">Resource keys have the suffix `Key` appended to the property name.</span></span>  
  
 <span data-ttu-id="d0878-111">下面的示例演示如何访问和使用的静态值<xref:System.Windows.SystemParameters>来设计或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="d0878-111">The following example shows how to access and use the static values of <xref:System.Windows.SystemParameters> to style or customize a button.</span></span> <span data-ttu-id="d0878-112">此标记示例通过应用大小按钮<xref:System.Windows.SystemParameters>至一个按钮的值。</span><span class="sxs-lookup"><span data-stu-id="d0878-112">This markup example sizes a button by applying <xref:System.Windows.SystemParameters> values to a button.</span></span>  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 <span data-ttu-id="d0878-113">若要使用的值<xref:System.Windows.SystemParameters>在代码中，你无需使用的静态引用或动态资源引用。</span><span class="sxs-lookup"><span data-stu-id="d0878-113">To use the values of <xref:System.Windows.SystemParameters> in code, you do not have to use either static references or dynamic resource references.</span></span> <span data-ttu-id="d0878-114">相反，使用的值<xref:System.Windows.SystemParameters>类。</span><span class="sxs-lookup"><span data-stu-id="d0878-114">Instead, use the values of the <xref:System.Windows.SystemParameters> class.</span></span> <span data-ttu-id="d0878-115">虽然非键属性已明确定义为静态属性的运行时行为[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]承载的系统将实时重新计算属性，并将正确的系统值对面向用户的更改的帐户。</span><span class="sxs-lookup"><span data-stu-id="d0878-115">Although the non-key properties are apparently defined as static properties, the runtime behavior of [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] as hosted by the system will reevaluate the properties in realtime, and will properly account for user-driven changes to system values.</span></span> <span data-ttu-id="d0878-116">下面的示例演示如何通过使用设置的宽度和按钮的高度<xref:System.Windows.SystemParameters>值。</span><span class="sxs-lookup"><span data-stu-id="d0878-116">The following example shows how to set the width and height of a button by using <xref:System.Windows.SystemParameters> values.</span></span>  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a><span data-ttu-id="d0878-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0878-117">See Also</span></span>  
 <xref:System.Windows.SystemParameters>  
 [<span data-ttu-id="d0878-118">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="d0878-118">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="d0878-119">使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="d0878-119">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="d0878-120">使用系统参数键</span><span class="sxs-lookup"><span data-stu-id="d0878-120">Use System Parameters Keys</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [<span data-ttu-id="d0878-121">帮助主题</span><span class="sxs-lookup"><span data-stu-id="d0878-121">How-to Topics</span></span>](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
