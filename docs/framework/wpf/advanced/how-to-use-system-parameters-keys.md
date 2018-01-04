---
title: "如何：使用系统参数键"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0b2a7352540456b459428dd87f6c60be0b8bc08b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-system-parameters-keys"></a><span data-ttu-id="32484-102">如何：使用系统参数键</span><span class="sxs-lookup"><span data-stu-id="32484-102">How to: Use System Parameters Keys</span></span>
<span data-ttu-id="32484-103">系统资源将多个系统规格以资源的形式公开，以帮助开发人员创建与系统设置一致的视觉效果。</span><span class="sxs-lookup"><span data-stu-id="32484-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="32484-104"><xref:System.Windows.SystemParameters>是一个类，包含系统参数值和绑定到这些值的资源键 — 例如，<xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A>和<xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="32484-104"><xref:System.Windows.SystemParameters> is a class that contains both system parameter values and resource keys that bind to the values—for example, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> and <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>.</span></span> <span data-ttu-id="32484-105">系统参数规格可用作静态或动态资源。</span><span class="sxs-lookup"><span data-stu-id="32484-105">System parameter metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="32484-106">如果希望参数规格在应用程序运行时自动更新，请使用动态资源；否则，请使用静态资源。</span><span class="sxs-lookup"><span data-stu-id="32484-106">Use a dynamic resource if you want the parameter metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="32484-107">动态资源具有关键字*密钥*追加到属性名称。</span><span class="sxs-lookup"><span data-stu-id="32484-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="32484-108">以下示例演示如何访问和使用系统参数动态资源来设计按钮样式或自定义按钮。</span><span class="sxs-lookup"><span data-stu-id="32484-108">The following example shows how to access and use system parameter dynamic resources to style or customize a button.</span></span> <span data-ttu-id="32484-109">这[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]示例调整按钮通过分配的大小<xref:System.Windows.SystemParameters>值与按钮的宽度和高度。</span><span class="sxs-lookup"><span data-stu-id="32484-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example sizes a button by assigning <xref:System.Windows.SystemParameters> values to the button's width and height.</span></span>  
  
## <a name="example"></a><span data-ttu-id="32484-110">示例</span><span class="sxs-lookup"><span data-stu-id="32484-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="32484-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="32484-111">See Also</span></span>  
 [<span data-ttu-id="32484-112">使用系统画笔绘制区域</span><span class="sxs-lookup"><span data-stu-id="32484-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="32484-113">使用 SystemFonts</span><span class="sxs-lookup"><span data-stu-id="32484-113">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [<span data-ttu-id="32484-114">使用 SystemParameters</span><span class="sxs-lookup"><span data-stu-id="32484-114">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
