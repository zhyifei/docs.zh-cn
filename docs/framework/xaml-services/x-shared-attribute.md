---
title: "x:Shared 特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
caps.latest.revision: "16"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d6a9333b2267e82fc25b2a0ec4bf5dd14f644078
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="xshared-attribute"></a><span data-ttu-id="2c1fc-102">x:Shared 特性</span><span class="sxs-lookup"><span data-stu-id="2c1fc-102">x:Shared Attribute</span></span>
<span data-ttu-id="2c1fc-103">当设置为`false`，修改 WPF 资源检索行为，以便对特性化的资源的请求创建的每个请求而不是共享同一个实例的所有请求的新实例。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="2c1fc-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="2c1fc-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="2c1fc-105">备注</span><span class="sxs-lookup"><span data-stu-id="2c1fc-105">Remarks</span></span>  
 <span data-ttu-id="2c1fc-106">`x:Shared`将映射到 XAML 语言 XAML 命名空间，由.NET Framework XAML 服务和其 XAML 读取器识别为有效的 XAML 语言元素。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="2c1fc-107">但是的规定的功能`x:Shared`时才有意义的 WPF 应用程序和 WPF XAML 分析器。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="2c1fc-108">在 WPF 中，`x:Shared`当应用于在 WPF 中是否存在的对象时才有用作为特性<xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="2c1fc-109">分析异常或其他错误，不会引发其他用法，但它们不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="2c1fc-110">含义`x:Shared`XAML 语言规范中未指定。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="2c1fc-111">其他 XAML 实现中的，如基于.NET Framework XAML 服务，不一定支持资源共享。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="2c1fc-112">此类的 XAML 实现可以提供类似的行为，也使用的支持框架中`x:Shared`值。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="2c1fc-113">在 WPF 中，默认值`x:Shared`资源的条件是`true`。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="2c1fc-114">这种情况意味着任何给定的资源请求始终返回同一个实例。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="2c1fc-115">修改资源 API，通过等返回的对象<xref:System.Windows.FrameworkElement.FindResource%2A>，或修改内的对象直接<xref:System.Windows.ResourceDictionary>，更改原始资源。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="2c1fc-116">如果对该资源的引用是动态资源引用，该资源的使用者将获取已更改的资源。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="2c1fc-117">如果对资源的引用是静态资源引用，更改之后的资源为[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]处理时间是不相关。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="2c1fc-118">有关静态与动态资源引用的详细信息，请参阅[XAML 资源](../../../docs/framework/wpf/advanced/xaml-resources.md)。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-118">For more information about static versus dynamic resource references, see [XAML Resources](../../../docs/framework/wpf/advanced/xaml-resources.md).</span></span>  
  
 <span data-ttu-id="2c1fc-119">显式指定`x:Shared="true"`很少做，因为这已是默认值。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="2c1fc-120">没有直接代码的等效`x:Shared`WPF 中对象模型; 它仅可以在 XAML 用法中指定，并且必须处理由默认 WPF 行为，也可在加载路径上的中间 XAML 节点流如果使用.NET Framework XAML Se 处理服务和其 XAML 读取器。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="2c1fc-121">一种方案`x:Shared="false"`是如果你定义<xref:System.Windows.FrameworkElement>或<xref:System.Windows.FrameworkContentElement>派生类作为资源，然后将元素资源引入到内容模型。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="2c1fc-122">`x:Shared="false"`使引入多次相同集合中的元素资源 (如<xref:System.Windows.Controls.UIElementCollection>)。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="2c1fc-123">而无需`x:Shared="false"`这是无效的因为集合强制其内容的唯一性。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="2c1fc-124">但是，`x:Shared="false"`行为创建另一个的相同实例，而不是返回同一个实例的资源。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="2c1fc-125">另一方案`x:Shared="false"`是如果你使用<xref:System.Windows.Freezable>动画值但想要修改的每个动画基础上的资源的资源。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="2c1fc-126">字符串处理`false`不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="2c1fc-127">在 WPF 中，`x:Shared`才在以下情况下有效：</span><span class="sxs-lookup"><span data-stu-id="2c1fc-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
-   <span data-ttu-id="2c1fc-128"><xref:System.Windows.ResourceDictionary> ，其中包含的项`x:Shared`必须进行编译。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="2c1fc-129"><xref:System.Windows.ResourceDictionary>不能为宽松 XAML 中或用于主题。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
-   <span data-ttu-id="2c1fc-130"><xref:System.Windows.ResourceDictionary>包含的项必须不嵌套在另一个<xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="2c1fc-131">例如，不能使用`x:Shared`中的项<xref:System.Windows.ResourceDictionary>内<xref:System.Windows.Style>已<xref:System.Windows.ResourceDictionary>项。</span><span class="sxs-lookup"><span data-stu-id="2c1fc-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1fc-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c1fc-132">See Also</span></span>  
 <xref:System.Windows.ResourceDictionary>  
 [<span data-ttu-id="2c1fc-133">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="2c1fc-133">XAML Resources</span></span>](../../../docs/framework/wpf/advanced/xaml-resources.md)  
 [<span data-ttu-id="2c1fc-134">基元素</span><span class="sxs-lookup"><span data-stu-id="2c1fc-134">Base Elements</span></span>](../../../docs/framework/wpf/advanced/base-elements.md)
