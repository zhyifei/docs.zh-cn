---
title: 内联样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b88ef444283f4e1e85009c59b39f3cc41965d300
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460005"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="e1f94-102">内联样式和模板</span><span class="sxs-lookup"><span data-stu-id="e1f94-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="e1f94-103">提供 <xref:System.Windows.Style> 对象和模板对象（<xref:System.Windows.FrameworkTemplate> 子类）作为一种方法，用于在资源中定义元素的可视外观，以便可以多次使用它们。</span><span class="sxs-lookup"><span data-stu-id="e1f94-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="e1f94-104">出于此原因，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中采用类型 <xref:System.Windows.Style> 和 <xref:System.Windows.FrameworkTemplate> 的属性几乎始终对现有样式和模板进行资源引用，而不是以内联方式定义新的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="e1f94-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="e1f94-105">内联样式和模板的限制</span><span class="sxs-lookup"><span data-stu-id="e1f94-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="e1f94-106">在 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]中，从技术上讲，可以通过以下两种方式之一设置样式和模板属性。</span><span class="sxs-lookup"><span data-stu-id="e1f94-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="e1f94-107">您可以使用特性语法来引用资源中定义的样式，例如 `<`*对象*`Style="{StaticResource`*myResourceKey*`}" .../>`。</span><span class="sxs-lookup"><span data-stu-id="e1f94-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="e1f94-108">或者，可以使用属性元素语法来定义内联样式，例如：</span><span class="sxs-lookup"><span data-stu-id="e1f94-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="e1f94-109">`<`*对象*`>`</span><span class="sxs-lookup"><span data-stu-id="e1f94-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="e1f94-110">`<`*对象*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="e1f94-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="e1f94-111">`<` `Style``.../>`</span><span class="sxs-lookup"><span data-stu-id="e1f94-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="e1f94-112">`</`*对象*`.Style>`</span><span class="sxs-lookup"><span data-stu-id="e1f94-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="e1f94-113">`</`*对象*`>`</span><span class="sxs-lookup"><span data-stu-id="e1f94-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="e1f94-114">特性用法更常见。</span><span class="sxs-lookup"><span data-stu-id="e1f94-114">The attribute usage is much more common.</span></span> <span data-ttu-id="e1f94-115">在资源中以内联方式定义且未在资源中定义的样式必须仅限于包含元素，因为它没有资源键，所以不能轻易地重新使用。</span><span class="sxs-lookup"><span data-stu-id="e1f94-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="e1f94-116">通常，资源定义的样式更通用，更有用，更多的是将程序逻辑与代码中的程序逻辑分离的通用 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 编程模型原则。</span><span class="sxs-lookup"><span data-stu-id="e1f94-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="e1f94-117">通常，即使只是要在该位置使用该样式或模板，也没有理由设置样式或模板。</span><span class="sxs-lookup"><span data-stu-id="e1f94-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="e1f94-118">大多数可以采用样式或模板的元素也支持 content 属性和内容模型。</span><span class="sxs-lookup"><span data-stu-id="e1f94-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="e1f94-119">如果只使用通过样式设置或模板化一次创建的任何逻辑树，只需在直接标记中使用等效的子元素填充该内容属性即可。</span><span class="sxs-lookup"><span data-stu-id="e1f94-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="e1f94-120">这会完全跳过样式和模板机制。</span><span class="sxs-lookup"><span data-stu-id="e1f94-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="e1f94-121">对于样式和模板，也可以通过返回对象的标记扩展启用其他语法。</span><span class="sxs-lookup"><span data-stu-id="e1f94-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="e1f94-122">有两种可能的方案包括[TemplateBinding](templatebinding-markup-extension.md)和 <xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="e1f94-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1f94-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1f94-123">See also</span></span>

- [<span data-ttu-id="e1f94-124">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="e1f94-124">Styling and Templating</span></span>](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
