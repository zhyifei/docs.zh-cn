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
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243357"
---
# <a name="componentresourcekey-markup-extension"></a><span data-ttu-id="ed6ec-102">ComponentResourceKey 标记扩展</span><span class="sxs-lookup"><span data-stu-id="ed6ec-102">ComponentResourceKey Markup Extension</span></span>
<span data-ttu-id="ed6ec-103">定义和引用从外部程序集加载的资源的键。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-103">Defines and references keys for resources that are loaded from external assemblies.</span></span> <span data-ttu-id="ed6ec-104">这使资源查找能够在程序集中指定目标类型，而不是在程序集或类上指定显式资源字典。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-104">This enables a resource lookup to specify a target type in an assembly, rather than an explicit resource dictionary in an assembly or on a class.</span></span>  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a><span data-ttu-id="ed6ec-105">XAML 属性用法（设置键，紧凑）</span><span class="sxs-lookup"><span data-stu-id="ed6ec-105">XAML Attribute Usage (setting key, compact)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a><span data-ttu-id="ed6ec-106">XAML 属性用法（设置键，详细）</span><span class="sxs-lookup"><span data-stu-id="ed6ec-106">XAML Attribute Usage (setting key, verbose)</span></span>  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a><span data-ttu-id="ed6ec-107">XAML 属性使用（请求资源，紧凑）</span><span class="sxs-lookup"><span data-stu-id="ed6ec-107">XAML Attribute Usage (requesting resource, compact)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a><span data-ttu-id="ed6ec-108">XAML 属性使用（请求资源，详细）</span><span class="sxs-lookup"><span data-stu-id="ed6ec-108">XAML Attribute Usage (requesting resource, verbose)</span></span>  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="ed6ec-109">XAML 值</span><span class="sxs-lookup"><span data-stu-id="ed6ec-109">XAML Values</span></span>  
  
|||  
|-|-|  
|`targetTypeName`|<span data-ttu-id="ed6ec-110">在资源程序集中定义的公共通用语言运行时 （CLR） 类型的名称。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-110">The name of the public common language runtime (CLR) type that is defined in the resource assembly.</span></span>|  
|`targetID`|<span data-ttu-id="ed6ec-111">资源的键。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-111">The key for the resource.</span></span> <span data-ttu-id="ed6ec-112">当资源被抬起来时`targetID`，将类似于资源的[x：Key 指令](../../../desktop-wpf/xaml-services/xkey-directive.md)。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-112">When resources are looked up, `targetID` will be analogous to the [x:Key Directive](../../../desktop-wpf/xaml-services/xkey-directive.md) of the resource.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ed6ec-113">备注</span><span class="sxs-lookup"><span data-stu-id="ed6ec-113">Remarks</span></span>  
 <span data-ttu-id="ed6ec-114">如上文用法所示，在以下两`ComponentResourceKey`个位置可以找到 [ 标记扩展用法：</span><span class="sxs-lookup"><span data-stu-id="ed6ec-114">As seen in the usages above, a {`ComponentResourceKey`} markup extension usage is found in two places:</span></span>  
  
- <span data-ttu-id="ed6ec-115">主题资源字典中键的定义，由控件作者提供。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-115">The definition of a key within a theme resource dictionary, as provided by a control author.</span></span>  
  
- <span data-ttu-id="ed6ec-116">从程序集访问主题资源时，当您重新模板化控件，但希望使用来自控件主题提供的资源的属性值时。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-116">Accessing a theme resource from the assembly, when you are retemplating the control but want to use property values that come from resources provided by the control's themes.</span></span>  
  
 <span data-ttu-id="ed6ec-117">对于引用来自主题的组件资源，通常建议您使用`{DynamicResource}`而不是`{StaticResource}`。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-117">For referencing component resources that come from themes, it is generally recommended that you use `{DynamicResource}` rather than `{StaticResource}`.</span></span> <span data-ttu-id="ed6ec-118">这在用法中显示。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-118">This is shown in the usages.</span></span> <span data-ttu-id="ed6ec-119">`{DynamicResource}`建议使用，因为用户可以更改主题本身。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-119">`{DynamicResource}` is recommended because the theme itself can be changed by the user.</span></span> <span data-ttu-id="ed6ec-120">如果希望与控件作者支持主题的意图最匹配的组件资源，则应使组件资源引用也是动态的。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-120">If you want the component resource that most closely matches the control author's intent for supporting a theme, you should enable your component resource reference to be dynamic also.</span></span>  
  
 <span data-ttu-id="ed6ec-121"><xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>标识目标程序集中存在的类型，其中实际定义了资源。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-121">The <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifies a type that exists in the target assembly where the resource is actually defined.</span></span> <span data-ttu-id="ed6ec-122">`ComponentResourceKey`可以定义和使用，而确切知道定义 的位置<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>，但最终必须通过引用的程序集解析类型。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-122">A `ComponentResourceKey` can be defined and used independently of knowing exactly where the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> is defined, but eventually must resolve the type through referenced assemblies.</span></span>  
  
 <span data-ttu-id="ed6ec-123">一个常用法<xref:System.Windows.ComponentResourceKey>种是定义密钥，然后作为类的成员公开。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-123">A common usage for <xref:System.Windows.ComponentResourceKey> is to define keys that are then exposed as members of a class.</span></span> <span data-ttu-id="ed6ec-124">对于此用法，<xref:System.Windows.ComponentResourceKey>请使用类构造函数，而不是标记扩展名。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-124">For this usage, you use the <xref:System.Windows.ComponentResourceKey> class constructor, not the markup extension.</span></span> <span data-ttu-id="ed6ec-125">有关详细信息，请参阅<xref:System.Windows.ComponentResourceKey>主题["控件创作概述](../controls/control-authoring-overview.md)"中的"主题资源定义和引用键"部分。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-125">For more information, see <xref:System.Windows.ComponentResourceKey>, or the "Defining and Referencing Keys for Theme Resources" section of the topic [Control Authoring Overview](../controls/control-authoring-overview.md).</span></span>  
  
 <span data-ttu-id="ed6ec-126">对于建立键和引用键控资源，属性语法通常用于`ComponentResourceKey`标记扩展。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-126">For both establishing keys and referencing keyed resources, attribute syntax is commonly used for the `ComponentResourceKey` markup extension.</span></span>  
  
 <span data-ttu-id="ed6ec-127">显示的紧凑语法依赖于标记扩展<xref:System.Windows.ComponentResourceKey.%23ctor%2A>的构造函数签名和位置参数用法。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-127">The compact syntax shown relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> constructor signature and positional parameter usage of a markup extension.</span></span> <span data-ttu-id="ed6ec-128">`targetTypeName`给出 的顺序`targetID`很重要。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-128">The order in which the `targetTypeName` and `targetID` are given is important.</span></span> <span data-ttu-id="ed6ec-129">详细语法依赖于无<xref:System.Windows.ComponentResourceKey.%23ctor%2A>参数构造函数，然后以类似于对象元素上的真实属性<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>语法<xref:System.Windows.ComponentResourceKey.ResourceId%2A>的方式设置 和。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-129">The verbose syntax relies on the <xref:System.Windows.ComponentResourceKey.%23ctor%2A> parameterless constructor, and then sets the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in a way that is analogous to a true attribute syntax on an object element.</span></span> <span data-ttu-id="ed6ec-130">在详细语法中，属性的设置顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-130">In the verbose syntax, the order in which the properties are set is not important.</span></span> <span data-ttu-id="ed6ec-131">这两种备选方案的关系和机制（紧凑和详细）在主题[标记扩展和WPF XAML](markup-extensions-and-wpf-xaml.md)中进行了更详细的描述。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-131">The relationship and mechanisms of these two alternatives (compact and verbose) is described in more detail in the topic [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="ed6ec-132">从技术上讲，的值`targetID`可以是任何对象，它不必是字符串。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-132">Technically, the value for `targetID` can be any object, it does not have to be a string.</span></span> <span data-ttu-id="ed6ec-133">但是，WPF 中最常见的用法是使`targetID`值与字符串的窗体对齐，以及此类字符串在[XamlName 语法](../../../desktop-wpf/xaml-services/xamlname-grammar.md)中有效的位置。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-133">However, the most common usage in WPF is to align the `targetID` value with forms that are strings, and where such strings are valid in the [XamlName Grammar](../../../desktop-wpf/xaml-services/xamlname-grammar.md).</span></span>  
  
 <span data-ttu-id="ed6ec-134">`ComponentResourceKey`可用于对象元素语法。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-134">`ComponentResourceKey` can be used in object element syntax.</span></span> <span data-ttu-id="ed6ec-135">在这种情况下，需要指定<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A>和<xref:System.Windows.ComponentResourceKey.ResourceId%2A>属性的值才能正确初始化扩展。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-135">In this case, specifying the value of both the <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> and <xref:System.Windows.ComponentResourceKey.ResourceId%2A> properties is required to properly initialize the extension.</span></span>  
  
 <span data-ttu-id="ed6ec-136">在[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]读取器实现中，此标记扩展的处理由<xref:System.Windows.ComponentResourceKey>类定义。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-136">In the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] reader implementation, the handling for this markup extension is defined by the <xref:System.Windows.ComponentResourceKey> class.</span></span>  
  
 <span data-ttu-id="ed6ec-137">`ComponentResourceKey` 是标记扩展。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-137">`ComponentResourceKey` is a markup extension.</span></span> <span data-ttu-id="ed6ec-138">当要求转义特性值应为非文本值或非处理程序名称时，通常会实现标记扩展，相对于只在某些类型或属性上放置类型转换器而言，此需求更具有全局性。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-138">Markup extensions are typically implemented when there is a requirement to escape attribute values to be other than literal values or handler names, and the requirement is more global than just putting type converters on certain types or properties.</span></span> <span data-ttu-id="ed6ec-139">[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 中的所有标记扩展在其特性语法中都使用 { 和 } 字符，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器通过这一约定确认标记扩展必须处理该特性。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-139">All markup extensions in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] use the { and } characters in their attribute syntax, which is the convention by which a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor recognizes that a markup extension must process the attribute.</span></span> <span data-ttu-id="ed6ec-140">有关详细信息，请参阅[标记扩展和 WPF XAML](markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="ed6ec-140">For more information, see [Markup Extensions and WPF XAML](markup-extensions-and-wpf-xaml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed6ec-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed6ec-141">See also</span></span>

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="ed6ec-142">控件创作概述</span><span class="sxs-lookup"><span data-stu-id="ed6ec-142">Control Authoring Overview</span></span>](../controls/control-authoring-overview.md)
- [<span data-ttu-id="ed6ec-143">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="ed6ec-143">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
- [<span data-ttu-id="ed6ec-144">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="ed6ec-144">Markup Extensions and WPF XAML</span></span>](markup-extensions-and-wpf-xaml.md)
