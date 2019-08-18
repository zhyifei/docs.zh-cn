---
title: mc:ProcessContent 特性
ms.date: 03/30/2017
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
ms.openlocfilehash: bc406659bec3fd8d5da87b597356a3411c7a2605
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567400"
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="f0dee-102">mc:ProcessContent 特性</span><span class="sxs-lookup"><span data-stu-id="f0dee-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="f0dee-103">指定哪些[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]元素仍应由相关的父元素处理内容, 即使因为指定了[mc: 可忽略属性](mc-ignorable-attribute.md), [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理程序可以忽略直接父元素。</span><span class="sxs-lookup"><span data-stu-id="f0dee-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](mc-ignorable-attribute.md).</span></span> <span data-ttu-id="f0dee-104">特性支持用于自定义命名空间映射[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和版本控制的标记兼容性。 `mc:ProcessContent`</span><span class="sxs-lookup"><span data-stu-id="f0dee-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="f0dee-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="f0dee-105">XAML Attribute Usage</span></span>  
  
```  
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
  
## <a name="xaml-values"></a><span data-ttu-id="f0dee-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="f0dee-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f0dee-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="f0dee-107">*ignorablePrefix*</span></span>|<span data-ttu-id="f0dee-108">根据 XML 1.0 规范的任何有效的前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="f0dee-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="f0dee-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="f0dee-109">*ignorableUri*</span></span>|<span data-ttu-id="f0dee-110">根据 XML 1.0 规范指定命名空间的任何有效 URI。</span><span class="sxs-lookup"><span data-stu-id="f0dee-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="f0dee-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="f0dee-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="f0dee-112">如果基础类型无法解析, 则[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]处理器实现可忽略的元素。</span><span class="sxs-lookup"><span data-stu-id="f0dee-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="f0dee-113">*[content]*</span><span class="sxs-lookup"><span data-stu-id="f0dee-113">*[content]*</span></span>|<span data-ttu-id="f0dee-114">*ThisElementCanBeIgnored*被标记为可忽略。</span><span class="sxs-lookup"><span data-stu-id="f0dee-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="f0dee-115">如果处理器忽略该元素, 则 *[content]* 由*对象*处理。</span><span class="sxs-lookup"><span data-stu-id="f0dee-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0dee-116">备注</span><span class="sxs-lookup"><span data-stu-id="f0dee-116">Remarks</span></span>  
 <span data-ttu-id="f0dee-117">默认情况下, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将忽略忽略元素内的内容。</span><span class="sxs-lookup"><span data-stu-id="f0dee-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="f0dee-118">您可以通过`mc:ProcessContent`指定特定元素, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将继续处理被忽略元素内的内容。</span><span class="sxs-lookup"><span data-stu-id="f0dee-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="f0dee-119">如果内容嵌套在多个标记中, 则通常会使用此方法, 其中至少一个标记为可忽略, 其中至少有一个不可忽略。</span><span class="sxs-lookup"><span data-stu-id="f0dee-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="f0dee-120">可以使用空格分隔符在属性中指定多个前缀, 例如: `mc:ProcessContent="ignore:Element1 ignore:Element2"`。</span><span class="sxs-lookup"><span data-stu-id="f0dee-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="f0dee-121">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]命名空间定义 SDK 的此区域中未记录的其他元素和特性。</span><span class="sxs-lookup"><span data-stu-id="f0dee-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="f0dee-122">有关详细信息, 请参阅[XML 标记兼容性规范](https://go.microsoft.com/fwlink/?LinkId=73824)。</span><span class="sxs-lookup"><span data-stu-id="f0dee-122">For more information, see [XML Markup Compatibility Specification](https://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0dee-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="f0dee-123">See also</span></span>

- [<span data-ttu-id="f0dee-124">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="f0dee-124">mc:Ignorable Attribute</span></span>](mc-ignorable-attribute.md)
- [<span data-ttu-id="f0dee-125">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="f0dee-125">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
