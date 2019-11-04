---
title: x:Shared 特性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: c820a9b1d9708e24b1460378199a6addc1e20899
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459923"
---
# <a name="xshared-attribute"></a><span data-ttu-id="c5cc9-102">x:Shared 特性</span><span class="sxs-lookup"><span data-stu-id="c5cc9-102">x:Shared Attribute</span></span>
<span data-ttu-id="c5cc9-103">如果设置为 "`false`"，则将修改 WPF 资源检索行为，以便对特性化资源的请求为每个请求创建一个新的实例，而不是为所有请求共享同一个实例。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c5cc9-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="c5cc9-104">XAML Attribute Usage</span></span>  
  
```xaml  
<ResourceDictionary>  
  <object x:Shared="false".../>  
</ResourceDictionary>  
```  
  
## <a name="remarks"></a><span data-ttu-id="c5cc9-105">备注</span><span class="sxs-lookup"><span data-stu-id="c5cc9-105">Remarks</span></span>  
 <span data-ttu-id="c5cc9-106">`x:Shared` 映射到 XAML 语言 XAML 命名空间，并通过 .NET Framework XAML 服务及其 XAML 读取器识别为有效的 XAML 语言元素。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET Framework XAML Services and its XAML readers.</span></span> <span data-ttu-id="c5cc9-107">但 `x:Shared` 的指定功能仅与 WPF 应用程序和 WPF XAML 分析器相关。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="c5cc9-108">在 WPF 中，`x:Shared` 仅在应用于 WPF <xref:System.Windows.ResourceDictionary>中存在的对象时用作特性。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="c5cc9-109">其他用法不会引发分析异常或其他错误，但它们不起作用。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>  
  
 <span data-ttu-id="c5cc9-110">XAML 语言规范中未指定 `x:Shared` 的含义。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="c5cc9-111">其他 XAML 实现（如 .NET Framework XAML 服务上构建的实现）不一定提供资源共享支持。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-111">Other XAML implementations, such as those that build on .NET Framework XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="c5cc9-112">此类 XAML 实现可以在支持框架中提供类似的行为，此行为也 `x:Shared` 值。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>  
  
 <span data-ttu-id="c5cc9-113">在 WPF 中，资源的默认 `x:Shared` 条件 `true`。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="c5cc9-114">这种情况意味着，任何给定的资源请求始终返回相同的实例。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-114">This condition means that any given resource request always returns the same instance.</span></span>  
  
 <span data-ttu-id="c5cc9-115">修改通过资源 API 返回的对象（如 <xref:System.Windows.FrameworkElement.FindResource%2A>）或直接在 <xref:System.Windows.ResourceDictionary>中修改对象会更改原始资源。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="c5cc9-116">如果对该资源的引用是动态资源引用，则该资源的使用者将获取更改的资源。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>  
  
 <span data-ttu-id="c5cc9-117">如果对资源的引用是静态资源引用，则 [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 处理时间之后对资源所做的更改是不相关的。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="c5cc9-118">有关静态和动态资源引用的详细信息，请参阅[XAML 资源](../../desktop-wpf/fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-118">For more information about static versus dynamic resource references, see [XAML Resources](../../desktop-wpf/fundamentals/xaml-resources-define.md).</span></span>  
  
 <span data-ttu-id="c5cc9-119">显式指定 `x:Shared="true"` 很少完成，因为它已是默认值。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="c5cc9-120">WPF 对象模型中的 `x:Shared` 没有直接的代码等效项;如果使用 .NET Framework XAML 服务及其 XAML 读取器进行处理，则它只能在 XAML 用法中指定，并且必须由默认的 WPF 行为或在加载路径的中间 XAML 节点流中处理。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET Framework XAML Services and its XAML readers.</span></span>  
  
 <span data-ttu-id="c5cc9-121">`x:Shared="false"` 方案适用于将 <xref:System.Windows.FrameworkElement> 或 <xref:System.Windows.FrameworkContentElement> 派生类定义为资源，然后将元素资源引入内容模型。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="c5cc9-122">`x:Shared="false"` 允许在同一集合中多次引入某个元素资源（如 <xref:System.Windows.Controls.UIElementCollection>）。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="c5cc9-123">无 `x:Shared="false"` 这是无效的，因为集合会强制其内容的唯一性。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="c5cc9-124">但 `x:Shared="false"` 行为会创建资源的另一个相同实例，而不是返回同一个实例。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>  
  
 <span data-ttu-id="c5cc9-125">`x:Shared="false"` 的另一种情况是，将 <xref:System.Windows.Freezable> 资源用于动画值，但要基于动画修改资源。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>  
  
 <span data-ttu-id="c5cc9-126">`false` 的字符串处理不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-126">The string handling of `false` is not case sensitive.</span></span>  
  
 <span data-ttu-id="c5cc9-127">在 WPF 中，`x:Shared` 仅在以下情况下有效：</span><span class="sxs-lookup"><span data-stu-id="c5cc9-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>  
  
- <span data-ttu-id="c5cc9-128">必须编译包含具有 `x:Shared` 的项的 <xref:System.Windows.ResourceDictionary>。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="c5cc9-129"><xref:System.Windows.ResourceDictionary> 不能位于松散 XAML 内或用于主题。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>  
  
- <span data-ttu-id="c5cc9-130">包含项的 <xref:System.Windows.ResourceDictionary> 不得嵌套在另一个 <xref:System.Windows.ResourceDictionary>中。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="c5cc9-131">例如，不能将 `x:Shared` 用于 <xref:System.Windows.ResourceDictionary> 处于已 <xref:System.Windows.ResourceDictionary> 项的 <xref:System.Windows.Style> 中的项。</span><span class="sxs-lookup"><span data-stu-id="c5cc9-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5cc9-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5cc9-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="c5cc9-133">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="c5cc9-133">XAML Resources</span></span>](../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="c5cc9-134">基元素</span><span class="sxs-lookup"><span data-stu-id="c5cc9-134">Base Elements</span></span>](../wpf/advanced/base-elements.md)
