---
title: "mc:ProcessContent 特性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: 2689b2c8-b4dc-4b71-b9bd-f95e619122d7
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1fe43e2450c35d976db7a188f854f7864f298afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="mcprocesscontent-attribute"></a><span data-ttu-id="db817-102">mc:ProcessContent 特性</span><span class="sxs-lookup"><span data-stu-id="db817-102">mc:ProcessContent Attribute</span></span>
<span data-ttu-id="db817-103">指定哪些[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]元素仍应具有处理相关的父元素的内容，即使可能忽略的直接父元素[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]由于指定的处理器[mc： 可忽略属性](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="db817-103">Specifies which [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] elements should still have content processed by relevant parent elements, even if the immediate parent element may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor due to specifying [mc:Ignorable Attribute](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md).</span></span> <span data-ttu-id="db817-104">`mc:ProcessContent`属性支持标记兼容性，为自定义命名空间映射和[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]版本控制。</span><span class="sxs-lookup"><span data-stu-id="db817-104">The `mc:ProcessContent` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="db817-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="db817-105">XAML Attribute Usage</span></span>  
  
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
  
## <a name="xaml-values"></a><span data-ttu-id="db817-106">XAML 值</span><span class="sxs-lookup"><span data-stu-id="db817-106">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db817-107">*ignorablePrefix*</span><span class="sxs-lookup"><span data-stu-id="db817-107">*ignorablePrefix*</span></span>|<span data-ttu-id="db817-108">根据 XML 1.0 规范任何有效的前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="db817-108">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="db817-109">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="db817-109">*ignorableUri*</span></span>|<span data-ttu-id="db817-110">任何有效的 URI，指定命名空间中的，根据 XML 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="db817-110">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="db817-111">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="db817-111">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="db817-112">可通过忽略的元素[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]处理器实现，如果基础类型不能解析。</span><span class="sxs-lookup"><span data-stu-id="db817-112">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
|<span data-ttu-id="db817-113">*[内容]*</span><span class="sxs-lookup"><span data-stu-id="db817-113">*[content]*</span></span>|<span data-ttu-id="db817-114">*ThisElementCanBeIgnored*标记可忽略。</span><span class="sxs-lookup"><span data-stu-id="db817-114">*ThisElementCanBeIgnored* is marked ignorable.</span></span> <span data-ttu-id="db817-115">如果处理器忽略该元素， *[内容]*由处理*对象*。</span><span class="sxs-lookup"><span data-stu-id="db817-115">If the processor ignores that element, *[content]* is processed by *object*.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db817-116">备注</span><span class="sxs-lookup"><span data-stu-id="db817-116">Remarks</span></span>  
 <span data-ttu-id="db817-117">默认情况下，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将忽略中被忽略的元素的内容。</span><span class="sxs-lookup"><span data-stu-id="db817-117">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="db817-118">你可以指定的特定元素由`mc:ProcessContent`，和一个[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将继续处理中被忽略的元素的内容。</span><span class="sxs-lookup"><span data-stu-id="db817-118">You can specify a specific element by `mc:ProcessContent`, and a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will continue to process the content within the ignored element.</span></span> <span data-ttu-id="db817-119">此值通常会在内容嵌套在多个标记，至少一个可以忽略，至少一个不是可忽略使用。</span><span class="sxs-lookup"><span data-stu-id="db817-119">This would typically be used if the content is nested within several tags, at least one of which is ignorable and at least one of which is not ignorable.</span></span>  
  
 <span data-ttu-id="db817-120">在属性中，例如使用空间分隔符，可指定多个前缀： `mc:ProcessContent="ignore:Element1 ignore:Element2"`。</span><span class="sxs-lookup"><span data-stu-id="db817-120">Multiple prefixes may be specified in the attribute, using a space separator, for example: `mc:ProcessContent="ignore:Element1 ignore:Element2"`.</span></span>  
  
 <span data-ttu-id="db817-121">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]命名空间定义其他元素和属性未记录的此区域内[!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="db817-121">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="db817-122">有关详细信息，请参阅[XML 标记兼容性规范](http://go.microsoft.com/fwlink/?LinkId=73824)。</span><span class="sxs-lookup"><span data-stu-id="db817-122">For more information, see [XML Markup Compatibility Specification](http://go.microsoft.com/fwlink/?LinkId=73824).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db817-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="db817-123">See Also</span></span>  
 [<span data-ttu-id="db817-124">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="db817-124">mc:Ignorable Attribute</span></span>](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)  
 [<span data-ttu-id="db817-125">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="db817-125">XAML Overview (WPF)</span></span>](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)
