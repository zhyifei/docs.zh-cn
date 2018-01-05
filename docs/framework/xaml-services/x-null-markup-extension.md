---
title: "x:Null 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- Null
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
caps.latest.revision: "20"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5b10d759a4f79eabe973a0fcd60736428e46f659
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="c6620-102">x:Null 标记扩展</span><span class="sxs-lookup"><span data-stu-id="c6620-102">x:Null Markup Extension</span></span>
<span data-ttu-id="c6620-103">指定`null`作为 XAML 成员的值。</span><span class="sxs-lookup"><span data-stu-id="c6620-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="c6620-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="c6620-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="c6620-105">备注</span><span class="sxs-lookup"><span data-stu-id="c6620-105">Remarks</span></span>  
 <span data-ttu-id="c6620-106">中的 null 引用的关键字[!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)]和[!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)]为 null。</span><span class="sxs-lookup"><span data-stu-id="c6620-106">The keyword for a null reference in [!INCLUDE[TLA#tla_cshrp](../../../includes/tlasharptla-cshrp-md.md)] and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="c6620-107">[!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)]关键字为空引用是`Nothing`，但始终使用`{x:Null}`作为 XAML 用法无论与 XAML 关联的代码隐藏语言。</span><span class="sxs-lookup"><span data-stu-id="c6620-107">The [!INCLUDE[TLA#tla_visualb](../../../includes/tlasharptla-visualb-md.md)] keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="c6620-108">`x:Null`标记扩展有任何可设置属性。</span><span class="sxs-lookup"><span data-stu-id="c6620-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="c6620-109">Null 的使用情况通常是与 CLR 的 XAML 成员透露关联<xref:System.Nullable%601>值。</span><span class="sxs-lookup"><span data-stu-id="c6620-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="c6620-110">`x:Null`标记扩展，所有 XAML 标记扩展，如使用大括号 (`{,}`) 的转义特性值应为非文本或事件处理程序引用的处理。</span><span class="sxs-lookup"><span data-stu-id="c6620-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="c6620-111">特性语法是最常用于该标记扩展的语法。</span><span class="sxs-lookup"><span data-stu-id="c6620-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="c6620-112">对象元素语法`<x:Null />`是从技术上讲是可行的但很少使用，因为`x:Null`标记扩展有无位置参数或构造自变量。</span><span class="sxs-lookup"><span data-stu-id="c6620-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="c6620-113">有关标记扩展的信息，请参阅[标记扩展和 WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="c6620-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="c6620-114">在.NET Framework XAML 服务，此标记扩展的处理的定义方法<xref:System.Windows.Markup.NullExtension>类。</span><span class="sxs-lookup"><span data-stu-id="c6620-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="c6620-115">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="c6620-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="c6620-116">请注意，`null`不一定是引用类型依赖项属性的初始未设置的值。</span><span class="sxs-lookup"><span data-stu-id="c6620-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="c6620-117">初始默认值可以为每个依赖项属性而异，并且可以基于特定属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="c6620-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="c6620-118">不接受许多依赖项属性`null`作为值，通过标记或由于其验证回调实现的代码。</span><span class="sxs-lookup"><span data-stu-id="c6620-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="c6620-119">有关依赖项属性的详细信息，请参阅[依赖项属性概述](../../../docs/framework/wpf/advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="c6620-119">For more information about dependency properties, see [Dependency Properties Overview](../../../docs/framework/wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6620-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6620-120">See Also</span></span>  
 <xref:System.Windows.DependencyProperty.UnsetValue>  
 [<span data-ttu-id="c6620-121">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="c6620-121">XAML Overview (WPF)</span></span>](../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [<span data-ttu-id="c6620-122">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="c6620-122">Markup Extensions and WPF XAML</span></span>](../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
