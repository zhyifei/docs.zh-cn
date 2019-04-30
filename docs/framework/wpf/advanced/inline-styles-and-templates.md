---
title: 内联样式和模板
ms.date: 03/30/2017
helpviewer_keywords:
- inline templates [WPF]
- styles [WPF], inline
- templates [WPF], inline
- inline styles [WPF]
ms.assetid: 69a1a3f9-acb5-4e2c-9c43-2e376c055ac4
ms.openlocfilehash: b566e157e2d4a9e9be21a678541bf5d5341a898c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62051003"
---
# <a name="inline-styles-and-templates"></a><span data-ttu-id="9ece4-102">内联样式和模板</span><span class="sxs-lookup"><span data-stu-id="9ece4-102">Inline Styles and Templates</span></span>
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="9ece4-103">提供了<xref:System.Windows.Style>对象和模板对象 (<xref:System.Windows.FrameworkTemplate>子类) 作为一种方式在资源中定义的元素的可视外观，以便它们可以使用多次。</span><span class="sxs-lookup"><span data-stu-id="9ece4-103">provides <xref:System.Windows.Style> objects and template objects (<xref:System.Windows.FrameworkTemplate> subclasses) as a way to define the visual appearance of an element in resources, so that they can be used multiple times.</span></span> <span data-ttu-id="9ece4-104">出于此原因中的属性[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]采用类型<xref:System.Windows.Style>和<xref:System.Windows.FrameworkTemplate>几乎总是进行对现有样式和模板的资源引用而不是内联定义新的。</span><span class="sxs-lookup"><span data-stu-id="9ece4-104">For this reason, attributes in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] that take the types <xref:System.Windows.Style> and <xref:System.Windows.FrameworkTemplate> almost always make resource references to existing styles and templates rather than define new ones inline.</span></span>  
  
## <a name="limitations-of-inline-styles-and-templates"></a><span data-ttu-id="9ece4-105">内联样式和模板的限制</span><span class="sxs-lookup"><span data-stu-id="9ece4-105">Limitations of Inline Styles and Templates</span></span>  
 <span data-ttu-id="9ece4-106">在[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]，可以从技术上讲中两种方式之一设置样式和模板属性。</span><span class="sxs-lookup"><span data-stu-id="9ece4-106">In [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], style and template properties can technically be set in one of two ways.</span></span> <span data-ttu-id="9ece4-107">您可以使用特性语法引用已在其中定义资源，例如样式`<`*对象*`Style="{StaticResource`*myResourceKey*`}" .../>`。</span><span class="sxs-lookup"><span data-stu-id="9ece4-107">You can use attribute syntax to reference a style that was defined within a resource, for example `<`*object*`Style="{StaticResource`*myResourceKey*`}" .../>`.</span></span> <span data-ttu-id="9ece4-108">或者，可以使用属性元素语法来定义内联样式，例如：</span><span class="sxs-lookup"><span data-stu-id="9ece4-108">Or you can use property element syntax to define a style inline, for instance:</span></span>  
  
 <span data-ttu-id="9ece4-109">`<` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="9ece4-109">`<` *object* `>`</span></span>  
  
 <span data-ttu-id="9ece4-110">`<` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="9ece4-110">`<` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="9ece4-111">`<` `Style`  `.../>`</span><span class="sxs-lookup"><span data-stu-id="9ece4-111">`<` `Style`  `.../>`</span></span>  
  
 <span data-ttu-id="9ece4-112">`</` *object* `.Style>`</span><span class="sxs-lookup"><span data-stu-id="9ece4-112">`</` *object* `.Style>`</span></span>  
  
 <span data-ttu-id="9ece4-113">`</` *object* `>`</span><span class="sxs-lookup"><span data-stu-id="9ece4-113">`</` *object* `>`</span></span>  
  
 <span data-ttu-id="9ece4-114">特性用法是更常见。</span><span class="sxs-lookup"><span data-stu-id="9ece4-114">The attribute usage is much more common.</span></span> <span data-ttu-id="9ece4-115">是以内联方式定义和未定义中资源的样式的一定范围限定为包含元素，且无法重新使用一样轻松因为它不有任何资源键。</span><span class="sxs-lookup"><span data-stu-id="9ece4-115">A style that is defined inline and not defined in resources is necessarily scoped to the containing element only, and cannot be re-used as easily because it has no resource key.</span></span> <span data-ttu-id="9ece4-116">一般情况下为资源定义的样式是更多情形且有用的并更符合一般原则是[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]编程模型将在代码中的程序逻辑分离从标记中的设计原则。</span><span class="sxs-lookup"><span data-stu-id="9ece4-116">In general a resource-defined style is more versatile and useful, and is more in keeping with the general [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] programming model principle of separating program logic in code from design in markup.</span></span>  
  
 <span data-ttu-id="9ece4-117">通常没有理由以设置内联样式或模板，即使只想要在该位置中使用该样式或模板。</span><span class="sxs-lookup"><span data-stu-id="9ece4-117">Usually there is no reason to set a style or template inline, even if you only intend to use that style or template in that location.</span></span> <span data-ttu-id="9ece4-118">可以采用的样式或模板的大多数元素还支持内容的属性和内容模型。</span><span class="sxs-lookup"><span data-stu-id="9ece4-118">Most elements that can take a style or template also support a content property and a content model.</span></span> <span data-ttu-id="9ece4-119">如果您仅使用任何逻辑树一次通过样式或模板创建，会更容易，只需直接标记中的等效子元素填充该内容属性。</span><span class="sxs-lookup"><span data-stu-id="9ece4-119">If you are only using whatever logical tree you create through styling or templating once, it would be even easier to just fill that content property with the equivalent child elements in direct markup.</span></span> <span data-ttu-id="9ece4-120">这会完全跳过的样式和模板机制。</span><span class="sxs-lookup"><span data-stu-id="9ece4-120">This would bypass the style and template mechanisms altogether.</span></span>  
  
 <span data-ttu-id="9ece4-121">其他情况下，返回的对象标记扩展启用的语法也可使用的样式和模板。</span><span class="sxs-lookup"><span data-stu-id="9ece4-121">Other syntaxes enabled by markup extensions that return an object are also possible for styles and templates.</span></span> <span data-ttu-id="9ece4-122">有可能的方案的两个此类扩展包括[TemplateBinding](templatebinding-markup-extension.md)和<xref:System.Windows.Data.Binding>。</span><span class="sxs-lookup"><span data-stu-id="9ece4-122">Two such extensions that have possible scenarios include [TemplateBinding](templatebinding-markup-extension.md) and <xref:System.Windows.Data.Binding>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ece4-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ece4-123">See also</span></span>

- [<span data-ttu-id="9ece4-124">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="9ece4-124">Styling and Templating</span></span>](../controls/styling-and-templating.md)
