---
title: ComponentResourceKey 标记扩展
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: 5f72d6c3273cfda4276383cfe72f90196e5d4340
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62037747"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="615d3-102">ComponentResourceKey 标记扩展</span><span class="sxs-lookup"><span data-stu-id="615d3-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="615d3-103">定义和引用从外部程序集加载的资源键。</span><span class="sxs-lookup"><span data-stu-id="615d3-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="615d3-104">这样一种资源查找程序集，而不是显式的资源字典在程序集或对类中指定目标类型。</span><span class="sxs-lookup"><span data-stu-id="615d3-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="615d3-105">XAML 特性用法 （设置键，compact）</span><span class="sxs-lookup"><span data-stu-id="615d3-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="615d3-106">XAML 特性用法 （设置键、 verbose）</span><span class="sxs-lookup"><span data-stu-id="615d3-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="615d3-107">XAML 特性用法 （请求资源，compact）</span><span class="sxs-lookup"><span data-stu-id="615d3-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="615d3-108">XAML 特性用法 （请求资源，详细）</span><span class="sxs-lookup"><span data-stu-id="615d3-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="615d3-109">XAML 值</span><span class="sxs-lookup"><span data-stu-id="615d3-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="615d3-110">公共名称[!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]资源程序集中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="615d3-110">The name of the public [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="615d3-111">资源键。</span><span class="sxs-lookup"><span data-stu-id="615d3-111">The key for the resource.</span></span> <span data-ttu-id="615d3-112">当资源查找`targetID`将类似于[X:key 指令](../../xaml-services/x-key-directive.md)的资源。</span><span class="sxs-lookup"><span data-stu-id="615d3-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../xaml-services/x-key-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="615d3-113">备注</span><span class="sxs-lookup"><span data-stu-id="615d3-113">Remarks</span></span>  
 <span data-ttu-id="615d3-114">如上面的用法中所示 {`ComponentResourceKey`} 标记扩展用法在两个位置找到：</span><span class="sxs-lookup"><span data-stu-id="615d3-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="615d3-115">内的主题资源字典，由控件作者提供的键的定义。</span><span class="sxs-lookup"><span data-stu-id="615d3-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="615d3-116">从程序集访问主题资源，当你重新模板化控件但想要使用来自控件的主题提供资源的属性值。</span><span class="sxs-lookup"><span data-stu-id="615d3-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="615d3-117">用于引用来自主题的组件资源，通常建议您使用`{DynamicResource}`而非`{StaticResource}`。</span><span class="sxs-lookup"><span data-stu-id="615d3-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="615d3-118">这是与用法中所示。</span><span class="sxs-lookup"><span data-stu-id="615d3-118">This is shown in the usages.</span></span> <span data-ttu-id="615d3-119">`{DynamicResource}` 建议，因为用户可以更改主题本身。</span><span class="sxs-lookup"><span data-stu-id="615d3-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="615d3-120">如果你想与支持该主题的控件作者的意图最匹配的组件资源，应启用组件资源参考，用于也是动态的。</span><span class="sxs-lookup"><span data-stu-id="615d3-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="615d3-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识存在于实际定义资源所在的目标集中的类型。</span><span class="sxs-lookup"><span data-stu-id="615d3-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="615d3-122">一个`ComponentResourceKey`可以定义和使用独立于完全了解其中<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>已定义，但最终必须解决通过引用的程序集的类型。</span><span class="sxs-lookup"><span data-stu-id="615d3-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="615d3-123">常见用法<xref:System.Windows.ComponentResourceKey>是定义键，然后公开为类的成员。</span><span class="sxs-lookup"><span data-stu-id="615d3-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="615d3-124">对于此用法中，你使用<xref:System.Windows.ComponentResourceKey>类构造函数，不是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="615d3-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="615d3-125">有关详细信息，请参阅<xref:System.Windows.ComponentResourceKey>，或主题的"定义和引用主题资源的键"部分[控件创作概述](../controls/control-authoring-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="615d3-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="615d3-126">有关建立键和引用键控资源，特性语法通常用于`ComponentResourceKey`标记扩展。</span><span class="sxs-lookup"><span data-stu-id="615d3-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="615d3-127">依赖于简洁的语法所示<xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>构造函数签名和标记扩展的位置参数用法。</span><span class="sxs-lookup"><span data-stu-id="615d3-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="615d3-128">依据的顺序`targetTypeName`和`targetID`提供非常重要。</span><span class="sxs-lookup"><span data-stu-id="615d3-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="615d3-129">详细语法依赖<xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>默认构造函数，然后设置<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>类似于在对象元素上的实际特性语法的方式。</span><span class="sxs-lookup"><span data-stu-id="615d3-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> default constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="615d3-130">在详细的语法中，将设置属性的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="615d3-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="615d3-131">主题中的更多详细信息中所述的以下两个替代方法 （compact 和 verbose） 机制以及关系[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="615d3-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="615d3-132">从技术上讲，值`targetID`可以是任何对象，它不需要为的字符串。</span><span class="sxs-lookup"><span data-stu-id="615d3-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="615d3-133">但是，在 WPF 中最常见的用法是对齐`targetID`值，该值具有窗体的字符串，并且其中此类字符串中可[XamlName 语法](../../xaml-services/xamlname-grammar.md)。</span><span class="sxs-lookup"><span data-stu-id="615d3-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="615d3-134">`ComponentResourceKey` 可以在对象元素语法中使用。</span><span class="sxs-lookup"><span data-stu-id="615d3-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="615d3-135">在这种情况下，指定的值都<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>正确初始化该扩展所需的属性。</span><span class="sxs-lookup"><span data-stu-id="615d3-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="615d3-136">在中[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器实现，对此标记扩展的处理由定义<xref:System.Windows.ComponentResourceKey>类。</span><span class="sxs-lookup"><span data-stu-id="615d3-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="615d3-137">`ComponentResourceKey` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="615d3-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="615d3-138">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="615d3-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="615d3-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="615d3-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="615d3-140">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="615d3-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="615d3-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="615d3-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="615d3-142">控件创作概述</span><span class="sxs-lookup"><span data-stu-id="615d3-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="615d3-143">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="615d3-143">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="615d3-144">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="615d3-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
