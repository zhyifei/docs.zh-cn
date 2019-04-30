---
title: DynamicResource 标记扩展
ms.date: 03/30/2017
f1_keywords:
- DynamicResource
- DynamicResourceExtension
helpviewer_keywords:
- XAML [WPF], DynamicResource markup extension
- DynamicResource markup extensions [WPF]
ms.assetid: 7324f243-03af-4c2b-b0db-26ac6cdfcbe4
ms.openlocfilehash: d07816718ebee2507f1888cffb70e6f8037bb996
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62010392"
---
# <a name="dynamicresource-markup-extension"></a><span data-ttu-id="e0e44-102">DynamicResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="e0e44-102">DynamicResource Markup Extension</span></span>
<span data-ttu-id="e0e44-103">提供值的任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通过推迟将对定义资源的引用值的属性特性。</span><span class="sxs-lookup"><span data-stu-id="e0e44-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by deferring that value to be a reference to a defined resource.</span></span> <span data-ttu-id="e0e44-104">类似于运行时查找该资源的查找行为。</span><span class="sxs-lookup"><span data-stu-id="e0e44-104">Lookup behavior for that resource is analogous to run-time lookup.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="e0e44-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="e0e44-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{DynamicResource key}" .../>  
```  
  
## <a name="xaml-property-element-usage"></a><span data-ttu-id="e0e44-106">XAML 属性元素用法</span><span class="sxs-lookup"><span data-stu-id="e0e44-106">XAML Property Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
    <DynamicResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e0e44-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="e0e44-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="e0e44-108">所请求资源的密钥。</span><span class="sxs-lookup"><span data-stu-id="e0e44-108">The key for the requested resource.</span></span> <span data-ttu-id="e0e44-109">最初由该键[X:key 指令](../../xaml-services/x-key-directive.md)如果资源已在标记中，或作为提供`key`参数调用时<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>如果资源在代码中创建的。</span><span class="sxs-lookup"><span data-stu-id="e0e44-109">This key was initially assigned by the [x:Key Directive](../../xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e0e44-110">备注</span><span class="sxs-lookup"><span data-stu-id="e0e44-110">Remarks</span></span>  
 <span data-ttu-id="e0e44-111">一个`DynamicResource`将创建初始编译期间的临时表达式并因此延迟的资源查找，直到实际需要来构造对象请求的资源值为止。</span><span class="sxs-lookup"><span data-stu-id="e0e44-111">A `DynamicResource` will create a temporary expression during the initial compilation and thus defer lookup for resources until the requested resource value is actually required in order to construct an object.</span></span> <span data-ttu-id="e0e44-112">这可能后[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]加载页面。</span><span class="sxs-lookup"><span data-stu-id="e0e44-112">This may potentially be after the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page is loaded.</span></span> <span data-ttu-id="e0e44-113">资源值将基于与当前的页范围，从开始的所有活动的资源字典的密钥搜索找到并替换为从编译的占位符表达式。</span><span class="sxs-lookup"><span data-stu-id="e0e44-113">The resource value will be found based on key search against all active resource dictionaries starting from the current page scope, and is substituted for the placeholder expression from compilation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e0e44-114">依赖关系属性在优先级方面，`DynamicResource`表达式等效于应用的动态资源引用的位置的位置。</span><span class="sxs-lookup"><span data-stu-id="e0e44-114">In terms of dependency property precedence, a `DynamicResource` expression is equivalent to the position where the dynamic resource reference is applied.</span></span> <span data-ttu-id="e0e44-115">如果将以前的属性的本地值`DynamicResource`作为本地值，表达式`DynamicResource`完全删除。</span><span class="sxs-lookup"><span data-stu-id="e0e44-115">If you set a local value for a property that previously had a `DynamicResource` expression as the local value, the `DynamicResource` is completely removed.</span></span> <span data-ttu-id="e0e44-116">有关详细信息，请参阅[依赖属性值优先级](dependency-property-value-precedence.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-116">For details, see [Dependency Property Value Precedence](dependency-property-value-precedence.md).</span></span>  
  
 <span data-ttu-id="e0e44-117">某些资源的访问方案是特别适合`DynamicResource`而不是[StaticResource 标记扩展](staticresource-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-117">Certain resource access scenarios are particularly appropriate for `DynamicResource` as opposed to a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span> <span data-ttu-id="e0e44-118">请参阅[XAML 资源](xaml-resources.md)有关的相对优点和性能产生的影响的讨论`DynamicResource`和`StaticResource`。</span><span class="sxs-lookup"><span data-stu-id="e0e44-118">See [XAML Resources](xaml-resources.md) for a discussion about the relative merits and performance implications of `DynamicResource` and `StaticResource`.</span></span>  
  
 <span data-ttu-id="e0e44-119">指定<xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>应该对应于现有的资源由[X:key 指令](../../xaml-services/x-key-directive.md)在您的页面、 应用程序、 可用的控件的主题和外部资源或系统资源，在某种程度上和查找资源也将按该顺序。</span><span class="sxs-lookup"><span data-stu-id="e0e44-119">The specified <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> should correspond to an existing resource determined by [x:Key Directive](../../xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources, and the resource lookup will happen in that order.</span></span> <span data-ttu-id="e0e44-120">有关静态和动态资源的资源查找的详细信息，请参阅[XAML 资源](xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-120">For more information about resource lookup for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="e0e44-121">资源键可以是任何字符串中定义[XamlName 语法](../../xaml-services/xamlname-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-121">A resource key may be any string defined in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="e0e44-122">资源键也可以是其他对象类型，如<xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="e0e44-122">A resource key may also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="e0e44-123">一个<xref:System.Type>密钥是如何可以由主题样式控件的基础。</span><span class="sxs-lookup"><span data-stu-id="e0e44-123">A <xref:System.Type> key is fundamental to how controls can be styled by themes.</span></span> <span data-ttu-id="e0e44-124">有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-124">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] <span data-ttu-id="e0e44-125">用于查找资源值，如<xref:System.Windows.FrameworkElement.FindResource%2A>，遵循所使用的相同的资源查找逻辑`DynamicResource`。</span><span class="sxs-lookup"><span data-stu-id="e0e44-125">for lookup of resource values, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, follow the same resource lookup logic as used by `DynamicResource`.</span></span>  
  
 <span data-ttu-id="e0e44-126">引用资源的可选声明性方式是作为[StaticResource 标记扩展](staticresource-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-126">The alternative declarative means of referencing a resource is as a [StaticResource Markup Extension](staticresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="e0e44-127">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="e0e44-127">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="e0e44-128">在 `DynamicResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.DynamicResourceExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="e0e44-128">The string token provided after the `DynamicResource` identifier string is assigned as the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.DynamicResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="e0e44-129">`DynamicResource` 可以在对象元素语法中使用。</span><span class="sxs-lookup"><span data-stu-id="e0e44-129">`DynamicResource` can be used in object element syntax.</span></span> <span data-ttu-id="e0e44-130">在这种情况下，指定的值<xref:System.Windows.DynamicResourceExtension.ResourceKey%2A>属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="e0e44-130">In this case, specifying the value of the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="e0e44-131">`DynamicResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：</span><span class="sxs-lookup"><span data-stu-id="e0e44-131">`DynamicResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.DynamicResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{DynamicResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="e0e44-132">如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。</span><span class="sxs-lookup"><span data-stu-id="e0e44-132">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="e0e44-133">由于 `DynamicResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。</span><span class="sxs-lookup"><span data-stu-id="e0e44-133">Because `DynamicResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="e0e44-134">在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现中，对此标记扩展的处理由定义<xref:System.Windows.DynamicResourceExtension>类。</span><span class="sxs-lookup"><span data-stu-id="e0e44-134">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.DynamicResourceExtension> class.</span></span>  
  
 <span data-ttu-id="e0e44-135">`DynamicResource` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="e0e44-135">`DynamicResource` is a markup extension.</span></span> <span data-ttu-id="e0e44-136">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="e0e44-136">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="e0e44-137">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="e0e44-137">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="e0e44-138">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="e0e44-138">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0e44-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0e44-139">See also</span></span>

- [<span data-ttu-id="e0e44-140">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="e0e44-140">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="e0e44-141">资源和代码</span><span class="sxs-lookup"><span data-stu-id="e0e44-141">Resources and Code</span></span>](resources-and-code.md)
- [<span data-ttu-id="e0e44-142">x:Key 指令</span><span class="sxs-lookup"><span data-stu-id="e0e44-142">x:Key Directive</span></span>](../../xaml-services/x-key-directive.md)
- [<span data-ttu-id="e0e44-143">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="e0e44-143">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="e0e44-144">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="e0e44-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="e0e44-145">StaticResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="e0e44-145">StaticResource Markup Extension</span></span>](staticresource-markup-extension.md)
- [<span data-ttu-id="e0e44-146">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="e0e44-146">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
