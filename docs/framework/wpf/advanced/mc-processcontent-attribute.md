---
title: mc:ProcessContent 特性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: dde304cc2b9db9cb01f9264ca1359b8979512cfa
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458784"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="eb865-102">mc:ProcessContent 特性</span><span class="sxs-lookup"><span data-stu-id="eb865-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="eb865-103">指定哪些 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 元素仍应由相关的父元素处理内容，即使因为指定[mc：可忽略属性](mc-ignorable-attribute.md)，因为 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器可能会忽略直接父元素。</span><span class="sxs-lookup"><span data-stu-id="eb865-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="eb865-104">`mc:ProcessContent` 特性支持用于自定义命名空间映射和 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 版本控制的标记兼容性。</span><span class="sxs-lookup"><span data-stu-id="eb865-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="eb865-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="eb865-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...  
  mc:ProcessContent="ignorablePrefix:ThisElementCanBeIgnored"  
>  
    <ignorablePrefix:ThisElementCanBeIgnored>  
        [content]  
    </ignorablePrefix:ThisElementCanBeIgnored>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="eb865-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="eb865-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="eb865-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="eb865-107">*ignorablePrefix*</span></span>|<span data-ttu-id="eb865-108">根据 XML 1.0 规范的任何有效的前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="eb865-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="eb865-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="eb865-109">*ignorableUri*</span></span>|<span data-ttu-id="eb865-110">根据 XML 1.0 规范指定命名空间的任何有效 URI。</span><span class="sxs-lookup"><span data-stu-id="eb865-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="eb865-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="eb865-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="eb865-112">如果无法解析基础类型，则 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 处理器实现可忽略的元素。</span><span class="sxs-lookup"><span data-stu-id="eb865-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="eb865-113">*content*</span><span class="sxs-lookup"><span data-stu-id="eb865-113">*[content]*</span></span>|<span data-ttu-id="eb865-114">*ThisElementCanBeIgnored*被标记为可忽略。</span><span class="sxs-lookup"><span data-stu-id="eb865-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="eb865-115">如果处理器忽略该元素，则 *[content]* 由*对象*处理。</span><span class="sxs-lookup"><span data-stu-id="eb865-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb865-116">备注</span><span class="sxs-lookup"><span data-stu-id="eb865-116">Remarks</span></span>  
 <span data-ttu-id="eb865-117">默认情况下，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器将忽略忽略元素中的内容。</span><span class="sxs-lookup"><span data-stu-id="eb865-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="eb865-118">可以通过 `mc:ProcessContent`指定特定元素，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] 处理器将继续处理被忽略元素内的内容。</span><span class="sxs-lookup"><span data-stu-id="eb865-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="eb865-119">如果内容嵌套在多个标记中，则通常会使用此方法，其中至少一个标记为可忽略，其中至少有一个不可忽略。</span><span class="sxs-lookup"><span data-stu-id="eb865-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="eb865-120">可以使用空格分隔符在属性中指定多个前缀，例如： `mc:ProcessContent="ignore:Element1 ignore:Element2"`。</span><span class="sxs-lookup"><span data-stu-id="eb865-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="eb865-121">`http://schemas.openxmlformats.org/markup-compatibility/2006` 命名空间定义 SDK 的此区域中未记录的其他元素和特性。</span><span class="sxs-lookup"><span data-stu-id="eb865-121">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="eb865-122">有关详细信息，请参阅[XML 标记兼容性规范](https://go.microsoft.com/fwlink/?LinkId=73824)。</span><span class="sxs-lookup"><span data-stu-id="eb865-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb865-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb865-123">See also</span></span>

- [<span data-ttu-id="eb865-124">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="eb865-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="eb865-125">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="eb865-125">XAML Overview (WPF)</span></span>](../../../desktop-wpf/fundamentals/xaml.md)
