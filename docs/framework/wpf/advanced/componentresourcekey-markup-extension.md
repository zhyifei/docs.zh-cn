---
title: "ComponentResourceKey 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b7f959318c5991fea2df92ff8000e85345fb35ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="edd07-102">ComponentResourceKey 标记扩展</span><span class="sxs-lookup"><span data-stu-id="edd07-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="edd07-103">定义和引用从外部程序集加载的资源键。</span><span class="sxs-lookup"><span data-stu-id="edd07-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="edd07-104">这使得资源查找功能可以在一个程序集，而不是在程序集或在类上的显式资源字典中指定的目标类型。</span><span class="sxs-lookup"><span data-stu-id="edd07-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="edd07-105">XAML 属性用法 （设置键，compact）</span><span class="sxs-lookup"><span data-stu-id="edd07-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="edd07-106">（设置键、 详细） 的 XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="edd07-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="edd07-107">XAML 属性用法 （请求资源，compact）</span><span class="sxs-lookup"><span data-stu-id="edd07-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="edd07-108">XAML 属性用法 （请求资源，详细）</span><span class="sxs-lookup"><span data-stu-id="edd07-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="edd07-109">XAML 值</span><span class="sxs-lookup"><span data-stu-id="edd07-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="edd07-110">公共名称[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]中的资源程序集定义的类型。</span><span class="sxs-lookup"><span data-stu-id="edd07-110">The name of the public [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="edd07-111">资源键。</span><span class="sxs-lookup"><span data-stu-id="edd07-111">The key for the resource.</span></span> <span data-ttu-id="edd07-112">当资源查找时，`targetID`将类似于[X:key 指令](../../../../docs/framework/xaml-services/x-key-directive.md)的资源。</span><span class="sxs-lookup"><span data-stu-id="edd07-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../../../docs/framework/xaml-services/x-key-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edd07-113">备注</span><span class="sxs-lookup"><span data-stu-id="edd07-113">Remarks</span></span>  
 <span data-ttu-id="edd07-114">如上面的用法中所示 {`ComponentResourceKey`} 标记扩展用法在两个位置中找到：</span><span class="sxs-lookup"><span data-stu-id="edd07-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
-   <span data-ttu-id="edd07-115">内主题资源字典，由控件作者提供的键的定义。</span><span class="sxs-lookup"><span data-stu-id="edd07-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
-   <span data-ttu-id="edd07-116">从程序集访问主题资源，当你是重新模板化控件，但想要使用来自控件的主题提供资源的属性值。</span><span class="sxs-lookup"><span data-stu-id="edd07-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="edd07-117">用于引用来自主题的组件资源，通常建议您使用`{DynamicResource}`而非`{StaticResource}`。</span><span class="sxs-lookup"><span data-stu-id="edd07-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="edd07-118">这是与用法中所示。</span><span class="sxs-lookup"><span data-stu-id="edd07-118">This is shown in the usages.</span></span> <span data-ttu-id="edd07-119">`{DynamicResource}`建议，因为用户可以更改主题本身。</span><span class="sxs-lookup"><span data-stu-id="edd07-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="edd07-120">如果你想存储组件资源与支持该主题的控件作者意向最相匹配，则应启用组件资源参考，用于也会动态。</span><span class="sxs-lookup"><span data-stu-id="edd07-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="edd07-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识存在于实际定义资源所在的目标程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="edd07-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="edd07-122">A`ComponentResourceKey`可以定义和使用独立于完全了解其中<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>已定义，但最终必须解决通过引用的程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="edd07-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="edd07-123">常见用法<xref:System.Windows.ComponentResourceKey>是定义为类的成员的然后公开的密钥。</span><span class="sxs-lookup"><span data-stu-id="edd07-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="edd07-124">对于此用法中，你使用<xref:System.Windows.ComponentResourceKey>类构造函数，不是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="edd07-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="edd07-125">有关详细信息，请参阅<xref:System.Windows.ComponentResourceKey>，或主题的"定义和引用主题资源的键"部分[控件创作概述](../../../../docs/framework/wpf/controls/control-authoring-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="edd07-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../../../../docs/framework/wpf/controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="edd07-126">有关建立键和引用键控资源，特性语法通常用于`ComponentResourceKey`标记扩展。</span><span class="sxs-lookup"><span data-stu-id="edd07-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="edd07-127">所示的紧凑语法依赖于<xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>构造函数签名和标记扩展的位置参数用法。</span><span class="sxs-lookup"><span data-stu-id="edd07-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="edd07-128">顺序`targetTypeName`和`targetID`提供非常重要。</span><span class="sxs-lookup"><span data-stu-id="edd07-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="edd07-129">详细语法依赖于<xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>默认构造函数，然后设置<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>类似于的对象元素上的实际特性语法的方式。</span><span class="sxs-lookup"><span data-stu-id="edd07-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> default constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="edd07-130">在详细的语法中，将设置其属性的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="edd07-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="edd07-131">主题中的更多详细信息中所述的关系和以下两个替代方法 （compact 和详细） 机制[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="edd07-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="edd07-132">从技术上讲，值`targetID`可以是任何对象，它没有为一个字串符。</span><span class="sxs-lookup"><span data-stu-id="edd07-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="edd07-133">但是，在 WPF 中的最常见用法是对齐`targetID`窗体，是字符串，且此类字符串是在中有效的值[XamlName 语法](../../../../docs/framework/xaml-services/xamlname-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="edd07-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../../../docs/framework/xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="edd07-134">`ComponentResourceKey`可在对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="edd07-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="edd07-135">在这种情况下，指定的值都<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>正确初始化扩展所需的属性。</span><span class="sxs-lookup"><span data-stu-id="edd07-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="edd07-136">在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器实现，对此标记扩展的处理定义的<xref:System.Windows.ComponentResourceKey>类。</span><span class="sxs-lookup"><span data-stu-id="edd07-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="edd07-137">`ComponentResourceKey` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="edd07-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="edd07-138">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="edd07-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="edd07-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="edd07-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="edd07-140">有关详细信息，请参阅[标记扩展和 WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="edd07-140">For more information, see [Markup Extensions and WPF XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd07-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edd07-141">See Also</span></span>  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [<span data-ttu-id="edd07-142">控件创作概述</span><span class="sxs-lookup"><span data-stu-id="edd07-142">Control Authoring Overview</span></span>](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [<span data-ttu-id="edd07-143">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="edd07-143">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="edd07-144">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="edd07-144">Markup Extensions and WPF XAML</span></span>](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
