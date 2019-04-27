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
ms.openlocfilehash: 03439a2c4a1a4de375e90d0e5121e690541e2f0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61805128"
---
# <a name="mcignorable-attribute"></a><span data-ttu-id="84c88-102">mc:Ignorable 特性</span><span class="sxs-lookup"><span data-stu-id="84c88-102">mc:Ignorable Attribute</span></span>
<span data-ttu-id="84c88-103">指定哪些[!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]可能会忽略在标记文件中遇到的命名空间前缀[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器。</span><span class="sxs-lookup"><span data-stu-id="84c88-103">Specifies which [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefixes encountered in a markup file may be ignored by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="84c88-104">`mc:Ignorable`属性支持标记兼容性，对自定义的命名空间映射以及[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]版本控制。</span><span class="sxs-lookup"><span data-stu-id="84c88-104">The `mc:Ignorable` attribute supports markup compatibility both for custom namespace mapping and for [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] versioning.</span></span>  
  
## <a name="xaml-attribute-usage-single-prefix"></a><span data-ttu-id="84c88-105">XAML 特性用法 （单个前缀）</span><span class="sxs-lookup"><span data-stu-id="84c88-105">XAML Attribute Usage (Single Prefix)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix="ignorableUri"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-attribute-usage-two-prefixes"></a><span data-ttu-id="84c88-106">XAML 特性用法 （两个前缀）</span><span class="sxs-lookup"><span data-stu-id="84c88-106">XAML Attribute Usage (Two Prefixes)</span></span>  
  
```  
<object  
  xmlns:ignorablePrefix1="ignorableUri"  
  xmlns:ignorablePrefix2="ignorableUri2"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="ignorablePrefix1 ignorablePrefix2"...>  
    <ignorablePrefix1:ThisElementCanBeIgnored/>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="84c88-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="84c88-107">XAML Values</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="84c88-108">*ignorablePrefix、 ignorablePrefix1，等等。*</span><span class="sxs-lookup"><span data-stu-id="84c88-108">*ignorablePrefix, ignorablePrefix1, etc.*</span></span>|<span data-ttu-id="84c88-109">任何有效的前缀字符串，每个 XML 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="84c88-109">Any valid prefix string, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="84c88-110">*ignorableUri*</span><span class="sxs-lookup"><span data-stu-id="84c88-110">*ignorableUri*</span></span>|<span data-ttu-id="84c88-111">任何有效的 URI 指定一个命名空间，每个 XML 1.0 规范。</span><span class="sxs-lookup"><span data-stu-id="84c88-111">Any valid URI for designating a namespace, per the XML 1.0 specification.</span></span>|  
|<span data-ttu-id="84c88-112">*ThisElementCanBeIgnored*</span><span class="sxs-lookup"><span data-stu-id="84c88-112">*ThisElementCanBeIgnored*</span></span>|<span data-ttu-id="84c88-113">元素，可以忽略[!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]处理器实现中，如果基础类型不能被解析。</span><span class="sxs-lookup"><span data-stu-id="84c88-113">An element that can be ignored by [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] processor implementations, if the underlying type cannot be resolved.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84c88-114">备注</span><span class="sxs-lookup"><span data-stu-id="84c88-114">Remarks</span></span>  
 <span data-ttu-id="84c88-115">`mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]命名空间前缀是映射时要使用的建议的前缀约定[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]兼容性命名空间[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84c88-115">The `mc` [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] namespace prefix is the recommended prefix convention to use when mapping the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] compatibility namespace [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)].</span></span>  
  
 <span data-ttu-id="84c88-116">元素或属性的元素名称的前缀部分被视为`mc:Ignorable`不会引发错误时由处理[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器。</span><span class="sxs-lookup"><span data-stu-id="84c88-116">Elements or attributes where the prefix portion of the element name are identified as `mc:Ignorable` will not raise errors when processed by a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor.</span></span> <span data-ttu-id="84c88-117">如果该属性不能解析为基础类型或编程构造，则忽略该元素。</span><span class="sxs-lookup"><span data-stu-id="84c88-117">If that attribute could not be resolved to an underlying type or programming construct, then that element is ignored.</span></span> <span data-ttu-id="84c88-118">但是请注意，被忽略的元素仍可能生成其他分析错误，因为将会不处理该元素的负面影响的其他元素要求。</span><span class="sxs-lookup"><span data-stu-id="84c88-118">Note however that ignored elements might still generate additional parsing errors for additional element requirements that are side effects of that element not being processed.</span></span> <span data-ttu-id="84c88-119">例如，特定元素内容模型可能需要一个子元素，但指定的子元素是否在`mc:Ignorable`前缀和指定的子元素不能被解析为类型，则[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器可能引发错误。</span><span class="sxs-lookup"><span data-stu-id="84c88-119">For instance, a particular element content model might require exactly one child element, but if the specified child element was in an `mc:Ignorable` prefix, and the specified child element could not be resolved to a type, then the [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor might raise an error.</span></span>  
  
 <span data-ttu-id="84c88-120">`mc:Ignorable` 仅适用于命名空间映射为标识符字符串。</span><span class="sxs-lookup"><span data-stu-id="84c88-120">`mc:Ignorable` only applies to namespace mappings to identifier strings.</span></span> <span data-ttu-id="84c88-121">`mc:Ignorable` 不适用于命名空间映射到指定的程序集中[!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]命名空间和程序集 （或与程序集的当前可执行文件的默认值）。</span><span class="sxs-lookup"><span data-stu-id="84c88-121">`mc:Ignorable` does not apply to namespace mappings into assemblies, which specify a [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)] namespace and an assembly (or default to the current executable as the assembly).</span></span>  
  
 <span data-ttu-id="84c88-122">如果要实现[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器，处理器实现不能引发分析或处理的任何元素或属性由标识为前缀限定的类型解析错误`mc:Ignorable`。</span><span class="sxs-lookup"><span data-stu-id="84c88-122">If you are implementing a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor, your processor implementation must not raise parsing or processing errors on type resolution for any element or attribute that is qualified by a prefix that is identified as `mc:Ignorable`.</span></span> <span data-ttu-id="84c88-123">但仍可以引发作为是辅助的结果无法加载或处理，如前面给出的一个子元素示例某元素的异常。</span><span class="sxs-lookup"><span data-stu-id="84c88-123">But your processor implementation can still raise exceptions that are a secondary result of an element failing to load or be processed, such as the one-child element example given earlier.</span></span>  
  
 <span data-ttu-id="84c88-124">默认情况下，[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]处理器将忽略已忽略元素中的内容。</span><span class="sxs-lookup"><span data-stu-id="84c88-124">By default, a [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] processor will ignore content within an ignored element.</span></span> <span data-ttu-id="84c88-125">但是，可以指定其他属性， [mc: processcontent 特性](mc-processcontent-attribute.md)、 需要继续的处理中忽略了元素的下一个可用的父元素的内容。</span><span class="sxs-lookup"><span data-stu-id="84c88-125">However, you can specify an additional attribute, [mc:ProcessContent Attribute](mc-processcontent-attribute.md), to require continued processing of content within an ignored element by the next available parent element.</span></span>  
  
 <span data-ttu-id="84c88-126">可以使用一个或多个空白字符作为分隔符，例如在属性中指定多个前缀： `mc:Ignorable="ignore1 ignore2"`。</span><span class="sxs-lookup"><span data-stu-id="84c88-126">Multiple prefixes can be specified in the attribute, using one or more white-space characters as the separator, for example: `mc:Ignorable="ignore1 ignore2"`.</span></span>  

 <span data-ttu-id="84c88-127">[!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)]命名空间定义其他元素和属性的未记录的此区域内[!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="84c88-127">The [!INCLUDE[TLA#tla_mcxmlnsv1](../../../../includes/tlasharptla-mcxmlnsv1-md.md)] namespace defines other elements and attributes that are not documented within this area of the [!INCLUDE[TLA#tla_sdk](../../../../includes/tlasharptla-sdk-md.md)].</span></span> <span data-ttu-id="84c88-128">有关详细信息，请参阅[XML 标记兼容性规范](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification)。</span><span class="sxs-lookup"><span data-stu-id="84c88-128">For more information, see [XML Markup Compatibility Specification](/office/open-xml/introduction-to-markup-compatibility#markup-compatibility-in-the-open-xml-file-formats-specification).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84c88-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="84c88-129">See also</span></span>

- <xref:System.Windows.Markup.XamlReader>
- [<span data-ttu-id="84c88-130">PresentationOptions:Freeze 特性</span><span class="sxs-lookup"><span data-stu-id="84c88-130">PresentationOptions:Freeze Attribute</span></span>](presentationoptions-freeze-attribute.md)
- [<span data-ttu-id="84c88-131">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="84c88-131">XAML Overview (WPF)</span></span>](xaml-overview-wpf.md)
- [<span data-ttu-id="84c88-132">WPF 中的文档</span><span class="sxs-lookup"><span data-stu-id="84c88-132">Documents in WPF</span></span>](documents-in-wpf.md)
