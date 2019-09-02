---
title: mc:Ignorable 特性
ms.date: 03/30/2017
helpviewer_keywords:
- mc XML namespace prefix [WPF]
- mc:Ignorable attribute
- XML [WPF], mc namespace prefix
- XAML [WPF], mc:Ignorable attribute
- mc:ProcessContent attribute
- XAML [WPF], mc:ProcessContent attribute
ms.assetid: acd9a6ef-b7ca-4146-abb6-60f3b366e9ec
ms.openlocfilehash: b68909d94ad8cc5bba75b2c520db82c5ccf1b922
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "70206186"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="9ef59-102">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="9ef59-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="9ef59-103">指定在[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]标记文件中遇到的哪些命名空间前缀可能会被[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器忽略。</span><span class="sxs-lookup"><span data-stu-id="9ef59-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="9ef59-104">特性支持用于自定义命名空间映射[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]和版本控制的标记兼容性。 `mc:Ignorable`</span><span class="sxs-lookup"><span data-stu-id="9ef59-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="9ef59-105">XAML 特性用法 (单前缀)</span><span class="sxs-lookup"><span data-stu-id="9ef59-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="9ef59-106">XAML 特性用法 (两个前缀)</span><span class="sxs-lookup"><span data-stu-id="9ef59-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9ef59-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="9ef59-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9ef59-108">*ignorablePrefix、ignorablePrefix1 等。*</span><span class="sxs-lookup"><span data-stu-id="9ef59-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="9ef59-109">根据 XML 1.0 规范的任何有效的前缀字符串。</span><span class="sxs-lookup"><span data-stu-id="9ef59-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9ef59-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="9ef59-110">*ignorableUri*</span></span>|<span data-ttu-id="9ef59-111">根据 XML 1.0 规范指定命名空间的任何有效 URI。</span><span class="sxs-lookup"><span data-stu-id="9ef59-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="9ef59-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="9ef59-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="9ef59-113">如果基础类型无法解析, 则[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]处理器实现可忽略的元素。</span><span class="sxs-lookup"><span data-stu-id="9ef59-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ef59-114">备注</span><span class="sxs-lookup"><span data-stu-id="9ef59-114">Remarks</span></span>  
 <span data-ttu-id="9ef59-115">命名空间前缀是映射[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]兼容命名空间`http://schemas.openxmlformats.org/markup-compatibility/2006`时建议使用的前缀约定。 `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ef59-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace `http://schemas.openxmlformats.org/markup-compatibility/2006`.</span></span>  
  
 <span data-ttu-id="9ef59-116">元素名称的前缀部分标识为`mc:Ignorable`的元素或属性将不会在[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器处理时引发错误。</span><span class="sxs-lookup"><span data-stu-id="9ef59-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="9ef59-117">如果该特性未能解析为基础类型或编程构造, 则将忽略该元素。</span><span class="sxs-lookup"><span data-stu-id="9ef59-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="9ef59-118">但请注意, 如果忽略元素, 则忽略的元素可能仍会生成其他元素要求的分析错误。</span><span class="sxs-lookup"><span data-stu-id="9ef59-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="9ef59-119">例如, 特定的元素内容模型可能只需要一个子元素, 但如果指定的子元素在`mc:Ignorable`前缀中, 并且指定的子元素未能解析为类型, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]则处理器可能引发错误。</span><span class="sxs-lookup"><span data-stu-id="9ef59-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="9ef59-120">`mc:Ignorable`仅适用于命名空间到标识符字符串的映射。</span><span class="sxs-lookup"><span data-stu-id="9ef59-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="9ef59-121">`mc:Ignorable`不适用于将命名空间映射到程序集, 这些程序集指定 CLR 命名空间和程序集 (或作为程序集的当前可执行文件的默认值)。</span><span class="sxs-lookup"><span data-stu-id="9ef59-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a CLR namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="9ef59-122">如果要实现[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器, 处理器实现对于由标识为`mc:Ignorable`的前缀限定的任何元素或属性, 都不得引发分析或处理错误。</span><span class="sxs-lookup"><span data-stu-id="9ef59-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="9ef59-123">但您的处理器实现仍可能引发异常, 这些异常是无法加载或处理元素的辅助结果, 如前面给出的一个子元素示例。</span><span class="sxs-lookup"><span data-stu-id="9ef59-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="9ef59-124">默认情况下, [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将忽略忽略元素内的内容。</span><span class="sxs-lookup"><span data-stu-id="9ef59-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="9ef59-125">但是, 您可以指定一个附加属性[mc: ProcessContent 特性](mc-processcontent-attribute.md), 以要求在下一个可用的父元素中继续处理被忽略元素内的内容。</span><span class="sxs-lookup"><span data-stu-id="9ef59-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="9ef59-126">可以使用一个或多个空白字符作为分隔符, 在属性中指定多个前缀, 例如: `mc:Ignorable="ignore1 ignore2"`。</span><span class="sxs-lookup"><span data-stu-id="9ef59-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="9ef59-127">`http://schemas.openxmlformats.org/markup-compatibility/2006`命名空间定义 SDK 的此区域中未记录的其他元素和特性。</span><span class="sxs-lookup"><span data-stu-id="9ef59-127">The `http://schemas.openxmlformats.org/markup-compatibility/2006` namespace defines other elements and attributes that are not documented within this area of the SDK.</span></span> <span data-ttu-id="9ef59-128">有关详细信息, 请参阅[XML 标记兼容性规范](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)。</span><span class="sxs-lookup"><span data-stu-id="9ef59-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ef59-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ef59-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="9ef59-130">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="9ef59-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="9ef59-131">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="9ef59-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="9ef59-132">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="9ef59-132">Documents in WPF</span></span>](documents-in-wpf.md)
