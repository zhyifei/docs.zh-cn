---
title: "内联样式和模板"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5dccf0b274121ff4fe88c9270119a2f631ffcf29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="39df6-102">内联样式和模板</span><span class="sxs-lookup"><span data-stu-id="39df6-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]<span data-ttu-id="39df6-103">提供<xref:System.Windows.Style>对象和模板对象 (<xref:System.Windows.FrameworkTemplate>子类) 作为在资源中定义的元素的可视外观的方法，以便它们可以使用多次。</span><span class="sxs-lookup"><span data-stu-id="39df6-103"> provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="39df6-104">为此中的属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]它们采用类型<xref:System.Windows.Style>和<xref:System.Windows.FrameworkTemplate>几乎总是建立了对现有样式和模板的资源引用而不是内联定义新的。</span><span class="sxs-lookup"><span data-stu-id="39df6-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="39df6-105">内联样式和模板的限制</span><span class="sxs-lookup"><span data-stu-id="39df6-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="39df6-106">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，从技术上讲可以在两种方式之一设置样式和模板的属性。</span><span class="sxs-lookup"><span data-stu-id="39df6-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="39df6-107">你可以使用的特性语法来引用样式已在其中定义资源，例如`<`*对象*`Style="{StaticResource`*myResourceKey*`}" .../>`。</span><span class="sxs-lookup"><span data-stu-id="39df6-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="39df6-108">或者，可以使用属性元素语法来定义内联样式，例如：</span><span class="sxs-lookup"><span data-stu-id="39df6-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="39df6-109">`<`*对象*`>`</span><span class="sxs-lookup"><span data-stu-id="39df6-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="39df6-110">`<`*对象*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="39df6-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="39df6-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="39df6-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="39df6-112">`</`*对象*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="39df6-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="39df6-113">`</`*对象*`>`</span><span class="sxs-lookup"><span data-stu-id="39df6-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="39df6-114">特性用法是得更加常见。</span><span class="sxs-lookup"><span data-stu-id="39df6-114">The attribute usage is much more common.</span></span> <span data-ttu-id="39df6-115">样式会以内联方式定义和未定义中资源一定范围限定为仅包含的元素，不能重新使用一样轻松因为它具有没有资源键。</span><span class="sxs-lookup"><span data-stu-id="39df6-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="39df6-116">为资源定义的样式通常是更通用和有用，因此更符合常规[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]编程模型将在代码中的程序逻辑中分离从标记中的设计原则。</span><span class="sxs-lookup"><span data-stu-id="39df6-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="39df6-117">通常没有无需设置内联样式或模板，即使你只想要在该位置中使用该样式或模板。</span><span class="sxs-lookup"><span data-stu-id="39df6-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="39df6-118">可以采用样式或模板的大多数元素还支持内容的属性和内容模型。</span><span class="sxs-lookup"><span data-stu-id="39df6-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="39df6-119">如果你只使用任何逻辑树一次创建通过样式或模板，将能够更轻松地仅将该内容的属性填充直接标记中的等效子元素。</span><span class="sxs-lookup"><span data-stu-id="39df6-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="39df6-120">这将完全跳过的样式和模板的机制。</span><span class="sxs-lookup"><span data-stu-id="39df6-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="39df6-121">通过返回的对象的标记扩展其他语法也可使用的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="39df6-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="39df6-122">具有可能的方案的两个此类扩展包括[TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md)和<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="39df6-122">Two such extensions that have possible scenarios include [TemplateBinding](../../../../docs/framework/wpf/advanced/templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39df6-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="39df6-123">See Also</span></span>  
 [<span data-ttu-id="39df6-124">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="39df6-124">Styling and Templating</span></span>](../../../../docs/framework/wpf/controls/styling-and-templating.md)
