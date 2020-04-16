---
title: x:Shared 特性
ms.date: 03/30/2017
helpviewer_keywords:
- XAML [XAML Services], x:Shared attribute
- x:Shared attribute [XAML Services]
- Shared attribute in XAML [XAML Services]
ms.assetid: c8cff434-2785-405f-9f95-16deb34c9e64
ms.openlocfilehash: e1cd1d9db5c19decd840b433f986e0ba53557a8b
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432646"
---
# <a name="xshared-attribute"></a><span data-ttu-id="92e37-102">x:Shared 特性</span><span class="sxs-lookup"><span data-stu-id="92e37-102">x:Shared Attribute</span></span>

<span data-ttu-id="92e37-103">设置为 时`false`，将修改 WPF 资源检索行为，以便对属性化资源的请求为每个请求创建一个新实例，而不是为所有请求共享相同的实例。</span><span class="sxs-lookup"><span data-stu-id="92e37-103">When set to `false`, modifies WPF resource-retrieval behavior so that requests for the attributed resource create a new instance for each request instead of sharing the same instance for all requests.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="92e37-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="92e37-104">XAML Attribute Usage</span></span>

```xaml
<ResourceDictionary>
  <object x:Shared="false".../>
</ResourceDictionary>
```

## <a name="remarks"></a><span data-ttu-id="92e37-105">备注</span><span class="sxs-lookup"><span data-stu-id="92e37-105">Remarks</span></span>

<span data-ttu-id="92e37-106">`x:Shared`映射到 XAML 语言 XAML 命名空间，并由 .NET XAML 服务及其 XAML 读取器识别为有效的 XAML 语言元素。</span><span class="sxs-lookup"><span data-stu-id="92e37-106">`x:Shared` is mapped to the XAML language XAML namespace and is recognized as a valid XAML language element by .NET XAML Services and its XAML readers.</span></span> <span data-ttu-id="92e37-107">但是，声明`x:Shared`的功能仅与 WPF 应用程序和 WPF XAML 解析器相关。</span><span class="sxs-lookup"><span data-stu-id="92e37-107">However, the stated capabilities of `x:Shared` are only relevant for WPF applications and for the WPF XAML parser.</span></span> <span data-ttu-id="92e37-108">在 WPF`x:Shared`中，仅当属性应用于存在于 WPF<xref:System.Windows.ResourceDictionary>中的对象时，它才可用作属性。</span><span class="sxs-lookup"><span data-stu-id="92e37-108">In WPF, `x:Shared` is only useful as an attribute when it is applied to an object that exists within a WPF <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="92e37-109">其他用法不会引发解析异常或其他错误，但它们没有效果。</span><span class="sxs-lookup"><span data-stu-id="92e37-109">Other usages do not throw parse exceptions or other errors, but they have no effect.</span></span>

<span data-ttu-id="92e37-110">在 XAML 语言规范中未指定 其`x:Shared`含义。</span><span class="sxs-lookup"><span data-stu-id="92e37-110">The meaning of `x:Shared` is not specified in the XAML language specification.</span></span> <span data-ttu-id="92e37-111">其他 XAML 实现（例如基于 .NET XAML 服务实现）不一定提供资源共享支持。</span><span class="sxs-lookup"><span data-stu-id="92e37-111">Other XAML implementations, such as those that build on .NET XAML Services, do not necessarily provide resource-sharing support.</span></span> <span data-ttu-id="92e37-112">此类 XAML 实现可以在支持框架中提供类似的行为，该框架`x:Shared`也使用值。</span><span class="sxs-lookup"><span data-stu-id="92e37-112">Such XAML implementations could provide similar behavior in the supporting framework that also used `x:Shared` values.</span></span>

<span data-ttu-id="92e37-113">在 WPF 中`x:Shared`，资源的默认条件是`true`。</span><span class="sxs-lookup"><span data-stu-id="92e37-113">In WPF, the default `x:Shared` condition for resources is `true`.</span></span> <span data-ttu-id="92e37-114">此条件表示任何给定的资源请求始终返回同一实例。</span><span class="sxs-lookup"><span data-stu-id="92e37-114">This condition means that any given resource request always returns the same instance.</span></span>

<span data-ttu-id="92e37-115">修改通过资源 API 返回的对象（如 ，或<xref:System.Windows.FrameworkElement.FindResource%2A>直接修改 中的对象<xref:System.Windows.ResourceDictionary>）会更改原始资源。</span><span class="sxs-lookup"><span data-stu-id="92e37-115">Modifying an object that is returned through a resource API, such as <xref:System.Windows.FrameworkElement.FindResource%2A>, or modifying an object directly within a <xref:System.Windows.ResourceDictionary>, changes the original resource.</span></span> <span data-ttu-id="92e37-116">如果对该资源的引用是动态资源引用，则该资源的使用者将获取已更改的资源。</span><span class="sxs-lookup"><span data-stu-id="92e37-116">If references to that resource were dynamic resource references, the consumers of that resource get the changed resource.</span></span>

<span data-ttu-id="92e37-117">如果对资源的引用是静态资源引用，则处理时间后[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)]对资源的更改不相关。</span><span class="sxs-lookup"><span data-stu-id="92e37-117">If references to the resource were static resource references, changes to the resource after [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] processing time are irrelevant.</span></span> <span data-ttu-id="92e37-118">有关静态资源引用和动态资源引用的详细信息，请参阅[XAML 资源](../fundamentals/xaml-resources-define.md)。</span><span class="sxs-lookup"><span data-stu-id="92e37-118">For more information about static versus dynamic resource references, see [XAML Resources](../fundamentals/xaml-resources-define.md).</span></span>

<span data-ttu-id="92e37-119">显式指定`x:Shared="true"`很少完成，因为这已经是默认值。</span><span class="sxs-lookup"><span data-stu-id="92e37-119">Explicitly specifying `x:Shared="true"` is rarely done, because that is already the default.</span></span> <span data-ttu-id="92e37-120">在 WPF 对象模型中`x:Shared`没有直接代码等效;它只能在 XAML 用法中指定，并且如果使用 .NET XAML 服务及其 XAML 读取器进行处理，则必须通过默认的 WPF 行为或在负载路径上的中间 XAML 节点流中进行处理。</span><span class="sxs-lookup"><span data-stu-id="92e37-120">There is no direct code equivalent for `x:Shared` in the WPF object model; it can only be specified in a XAML usage and must be processed either by the default WPF behavior or in an intermediate XAML node stream on the load path if processed using .NET XAML Services and its XAML readers.</span></span>

<span data-ttu-id="92e37-121">的方案`x:Shared="false"`是，如果将 或<xref:System.Windows.FrameworkElement><xref:System.Windows.FrameworkContentElement>派生类定义为资源，然后将元素资源引入内容模型。</span><span class="sxs-lookup"><span data-stu-id="92e37-121">A scenario for `x:Shared="false"` is if you define a <xref:System.Windows.FrameworkElement> or <xref:System.Windows.FrameworkContentElement> derived class as a resource and then you introduce the element resource into a content model.</span></span> <span data-ttu-id="92e37-122">`x:Shared="false"`使元素资源在同一集合（如<xref:System.Windows.Controls.UIElementCollection>） 中多次引入。</span><span class="sxs-lookup"><span data-stu-id="92e37-122">`x:Shared="false"` enables an element resource to be introduced multiple times in the same collection (such as a <xref:System.Windows.Controls.UIElementCollection>).</span></span> <span data-ttu-id="92e37-123">如果没有`x:Shared="false"`此选项无效，因为集合会强制其内容的唯一性。</span><span class="sxs-lookup"><span data-stu-id="92e37-123">Without `x:Shared="false"` this is invalid because the collection enforces uniqueness of its contents.</span></span> <span data-ttu-id="92e37-124">但是，该`x:Shared="false"`行为将创建资源的另一个相同实例，而不是返回相同的实例。</span><span class="sxs-lookup"><span data-stu-id="92e37-124">However, the `x:Shared="false"` behavior creates another identical instance of the resource instead of returning the same instance.</span></span>

<span data-ttu-id="92e37-125">的另一<xref:System.Windows.Freezable>个`x:Shared="false"`方案是，如果将资源用于动画值，但希望根据每个动画修改资源。</span><span class="sxs-lookup"><span data-stu-id="92e37-125">Another scenario for `x:Shared="false"` is if you use a <xref:System.Windows.Freezable> resource for animation values but want to modify the resource on a per animation basis.</span></span>

<span data-ttu-id="92e37-126">的`false`字符串处理不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="92e37-126">The string handling of `false` is not case sensitive.</span></span>

<span data-ttu-id="92e37-127">在 WPF`x:Shared`中，仅在以下条件下有效：</span><span class="sxs-lookup"><span data-stu-id="92e37-127">In WPF, `x:Shared` is only valid under the following conditions:</span></span>

- <span data-ttu-id="92e37-128"><xref:System.Windows.ResourceDictionary>必须编译包含 的`x:Shared`项。</span><span class="sxs-lookup"><span data-stu-id="92e37-128">The <xref:System.Windows.ResourceDictionary> that contains the items with `x:Shared` must be compiled.</span></span> <span data-ttu-id="92e37-129"><xref:System.Windows.ResourceDictionary>不能在松散的 XAML 内或用于主题。</span><span class="sxs-lookup"><span data-stu-id="92e37-129">The <xref:System.Windows.ResourceDictionary> cannot be within loose XAML or used for themes.</span></span>

- <span data-ttu-id="92e37-130"><xref:System.Windows.ResourceDictionary>包含项的 不能嵌套在另一个<xref:System.Windows.ResourceDictionary>中。</span><span class="sxs-lookup"><span data-stu-id="92e37-130">The <xref:System.Windows.ResourceDictionary> that contains the items must not be nested within another <xref:System.Windows.ResourceDictionary>.</span></span> <span data-ttu-id="92e37-131">例如`x:Shared`，不能用于<xref:System.Windows.ResourceDictionary>已属于<xref:System.Windows.Style><xref:System.Windows.ResourceDictionary>项 的 中的 项。</span><span class="sxs-lookup"><span data-stu-id="92e37-131">For example, you cannot use `x:Shared` for items in a <xref:System.Windows.ResourceDictionary> that is within a <xref:System.Windows.Style> that is already a <xref:System.Windows.ResourceDictionary> item.</span></span>

## <a name="see-also"></a><span data-ttu-id="92e37-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="92e37-132">See also</span></span>

- <xref:System.Windows.ResourceDictionary>
- [<span data-ttu-id="92e37-133">XAML 资源</span><span class="sxs-lookup"><span data-stu-id="92e37-133">XAML Resources</span></span>](../fundamentals/xaml-resources-define.md)
- [<span data-ttu-id="92e37-134">基元素</span><span class="sxs-lookup"><span data-stu-id="92e37-134">Base Elements</span></span>](../../framework/wpf/advanced/base-elements.md)
