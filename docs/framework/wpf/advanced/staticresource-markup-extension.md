---
title: StaticResource 标记扩展
ms.date: 03/30/2017
f1_keywords:
- StaticResource
- StaticResourceExtension
helpviewer_keywords:
- XAML [WPF], StaticResource markup extension
- StaticResource markup extensions [WPF]
ms.assetid: 97af044c-71f1-4617-9a94-9064b68185d2
ms.openlocfilehash: f3fb2559510d85f6e55a4784f2b528f16737a2ab
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371107"
---
# <a name="staticresource-markup-extension"></a><span data-ttu-id="e1283-102">StaticResource 标记扩展</span><span class="sxs-lookup"><span data-stu-id="e1283-102">StaticResource Markup Extension</span></span>
<span data-ttu-id="e1283-103">提供值的任何[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]通过查找对已定义资源的引用的属性特性。</span><span class="sxs-lookup"><span data-stu-id="e1283-103">Provides a value for any [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] property attribute by looking up a reference to an already defined resource.</span></span> <span data-ttu-id="e1283-104">对该资源的查找行为是类似于加载时查找，将在当前的标记从先前加载的资源查找[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]以及其他应用程序源页上，将生成与该资源值在运行时对象的属性值。</span><span class="sxs-lookup"><span data-stu-id="e1283-104">Lookup behavior for that resource is analogous to load-time lookup, which will look for resources that were previously loaded from the markup of the current [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] page as well as other application sources, and will generate that resource value as the property value in the run-time objects.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="e1283-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="e1283-105">XAML Attribute Usage</span></span>  
  
```xml  
<object property="{StaticResource key}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="e1283-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="e1283-106">XAML Object Element Usage</span></span>  
  
```xml  
<object>  
  <object.property>  
<StaticResource ResourceKey="key" .../>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="e1283-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="e1283-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`key`|<span data-ttu-id="e1283-108">所请求资源的密钥。</span><span class="sxs-lookup"><span data-stu-id="e1283-108">The key for the requested resource.</span></span> <span data-ttu-id="e1283-109">最初由该键[X:key 指令](../../xaml-services/x-key-directive.md)如果资源已在标记中，或作为提供`key`参数调用时<xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType>如果资源在代码中创建的。</span><span class="sxs-lookup"><span data-stu-id="e1283-109">This key was initially assigned by the [x:Key Directive](../../xaml-services/x-key-directive.md) if a resource was created in markup, or was provided as the `key` parameter when calling <xref:System.Windows.ResourceDictionary.Add%2A?displayProperty=nameWithType> if the resource was created in code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e1283-110">备注</span><span class="sxs-lookup"><span data-stu-id="e1283-110">Remarks</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e1283-111">一个`StaticResource`不能尝试使对资源定义前向引用在词法上进一步[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]文件。</span><span class="sxs-lookup"><span data-stu-id="e1283-111">A `StaticResource` must not attempt to make a forward reference to a resource that is defined lexically further within the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] file.</span></span> <span data-ttu-id="e1283-112">不支持尝试这样做，并且即使此类引用不会失败，尝试前向引用将会产生对加载时间性能产生负面影响时表示的内部哈希表<xref:System.Windows.ResourceDictionary>搜索。</span><span class="sxs-lookup"><span data-stu-id="e1283-112">Attempting to do so is not supported, and even if such a reference does not fail, attempting the forward reference will incur a load time performance penalty when the internal hash tables representing a <xref:System.Windows.ResourceDictionary> are searched.</span></span> <span data-ttu-id="e1283-113">为获得最佳结果，调整资源字典的组合，这样可以避免前向引用。</span><span class="sxs-lookup"><span data-stu-id="e1283-113">For best results, adjust the composition of your resource dictionaries such that forward references can be avoided.</span></span> <span data-ttu-id="e1283-114">如果无法避免前向引用，使用[DynamicResource 标记扩展](dynamicresource-markup-extension.md)相反。</span><span class="sxs-lookup"><span data-stu-id="e1283-114">If you cannot avoid a forward reference, use [DynamicResource Markup Extension](dynamicresource-markup-extension.md) instead.</span></span>  
  
 <span data-ttu-id="e1283-115">指定<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>应该对应于现有资源，以标识[X:key 指令](../../xaml-services/x-key-directive.md)页面、 应用程序，可用的控件的主题和外部资源或系统资源中的某个级别。</span><span class="sxs-lookup"><span data-stu-id="e1283-115">The specified <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> should correspond to an existing resource, identified with an [x:Key Directive](../../xaml-services/x-key-directive.md) at some level in your page, application, the available control themes and external resources, or system resources.</span></span> <span data-ttu-id="e1283-116">资源查找发生的顺序。</span><span class="sxs-lookup"><span data-stu-id="e1283-116">The resource lookup occurs in that order.</span></span> <span data-ttu-id="e1283-117">有关静态和动态资源的资源查找行为的详细信息，请参阅[XAML 资源](xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="e1283-117">For more information about resource lookup behavior for static and dynamic resources, see [XAML Resources](xaml-resources.md).</span></span>  
  
 <span data-ttu-id="e1283-118">资源键可以是任何字符串中定义[XamlName 语法](../../xaml-services/xamlname-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="e1283-118">A resource key can be any string defined in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span> <span data-ttu-id="e1283-119">资源键也可以是其他对象类型，如<xref:System.Type>。</span><span class="sxs-lookup"><span data-stu-id="e1283-119">A resource key can also be other object types, such as a <xref:System.Type>.</span></span> <span data-ttu-id="e1283-120">一个<xref:System.Type>密钥是如何控件可以设置的样式的主题，通过隐式样式项的基础。</span><span class="sxs-lookup"><span data-stu-id="e1283-120">A <xref:System.Type> key is fundamental to how controls can be styled by themes, through an implicit style key.</span></span> <span data-ttu-id="e1283-121">有关详细信息，请参阅[控件创作概述](../controls/control-authoring-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e1283-121">For more information, see [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="e1283-122">引用资源的可选声明性方式是作为[DynamicResource 标记扩展](dynamicresource-markup-extension.md)。</span><span class="sxs-lookup"><span data-stu-id="e1283-122">The alternative declarative means of referencing a resource is as a [DynamicResource Markup Extension](dynamicresource-markup-extension.md).</span></span>  
  
 <span data-ttu-id="e1283-123">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="e1283-123">Attribute syntax is the most common syntax used with this markup extension.</span></span> <span data-ttu-id="e1283-124">在 `StaticResource` 标识符字符串之后提供的字符串标记被指定为基础 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 扩展类的 <xref:System.Windows.StaticResourceExtension> 值。</span><span class="sxs-lookup"><span data-stu-id="e1283-124">The string token provided after the `StaticResource` identifier string is assigned as the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> value of the underlying <xref:System.Windows.StaticResourceExtension> extension class.</span></span>  
  
 <span data-ttu-id="e1283-125">`StaticResource` 可以在对象元素语法中使用。</span><span class="sxs-lookup"><span data-stu-id="e1283-125">`StaticResource` can be used in object element syntax.</span></span> <span data-ttu-id="e1283-126">在这种情况下，指定的值<xref:System.Windows.StaticResourceExtension.ResourceKey%2A>属性是必需的。</span><span class="sxs-lookup"><span data-stu-id="e1283-126">In this case, specifying the value of the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property is required.</span></span>  
  
 <span data-ttu-id="e1283-127">`StaticResource` 还可以在详细特性用法中使用，以便将 <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> 属性指定为一个 property=value 对：</span><span class="sxs-lookup"><span data-stu-id="e1283-127">`StaticResource` can also be used in a verbose attribute usage that specifies the <xref:System.Windows.StaticResourceExtension.ResourceKey%2A> property as a property=value pair:</span></span>  
  
```xml  
<object property="{StaticResource ResourceKey=key}" .../>  
```  
  
 <span data-ttu-id="e1283-128">如果扩展具有一个以上的可设置属性，或者某些属性是可选的，则详细用法通常会很有用。</span><span class="sxs-lookup"><span data-stu-id="e1283-128">The verbose usage is often useful for extensions that have more than one settable property, or if some properties are optional.</span></span> <span data-ttu-id="e1283-129">由于 `StaticResource` 仅有一个可设置的属性，并且此属性是必需的，因此该详细用法不具有典型性。</span><span class="sxs-lookup"><span data-stu-id="e1283-129">Because `StaticResource` has only one settable property, which is required, this verbose usage is not typical.</span></span>  
  
 <span data-ttu-id="e1283-130">在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器实现中，对此标记扩展的处理由定义<xref:System.Windows.StaticResourceExtension>类。</span><span class="sxs-lookup"><span data-stu-id="e1283-130">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor implementation, the handling for this markup extension is defined by the <xref:System.Windows.StaticResourceExtension> class.</span></span>  
  
 <span data-ttu-id="e1283-131">`StaticResource` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="e1283-131">`StaticResource` is a markup extension.</span></span> <span data-ttu-id="e1283-132">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="e1283-132">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="e1283-133">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="e1283-133">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="e1283-134">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="e1283-134">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1283-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="e1283-135">See also</span></span>
- [<span data-ttu-id="e1283-136">样式设置和模板化</span><span class="sxs-lookup"><span data-stu-id="e1283-136">Styling and Templating</span></span>](../controls/styling-and-templating.md)
- [<span data-ttu-id="e1283-137">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="e1283-137">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="e1283-138">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="e1283-138">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
- [<span data-ttu-id="e1283-139">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="e1283-139">XAML Resources</span></span>](xaml-resources.md)
- [<span data-ttu-id="e1283-140">资源和代码</span><span class="sxs-lookup"><span data-stu-id="e1283-140">Resources and Code</span></span>](resources-and-code.md)
