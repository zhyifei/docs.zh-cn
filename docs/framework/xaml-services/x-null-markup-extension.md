---
title: x:Null 标记扩展
ms.date: 03/30/2017
f1_keywords:
- NullExtension
- x:NullExtension
- x:Null
- "Null"
- xNull
helpviewer_keywords:
- Null markup extension in XAML [XAML Services]
- x:Null markup extension [XAML Services]
- XAML [XAML Services], x:Null markup extension
ms.assetid: 2e3ccc21-4996-481d-91b5-3910d8b3bfa3
ms.openlocfilehash: e46d8561b62d9137d4fed4df447338a97fc0577b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100803"
---
# <a name="xnull-markup-extension"></a><span data-ttu-id="86564-102">x:Null 标记扩展</span><span class="sxs-lookup"><span data-stu-id="86564-102">x:Null Markup Extension</span></span>
<span data-ttu-id="86564-103">指定`null`作为 XAML 成员的值。</span><span class="sxs-lookup"><span data-stu-id="86564-103">Specifies `null` as a value for a XAML member.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="86564-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="86564-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Null}" .../>  
```  
  
## <a name="remarks"></a><span data-ttu-id="86564-105">备注</span><span class="sxs-lookup"><span data-stu-id="86564-105">Remarks</span></span>  
 <span data-ttu-id="86564-106">中的空引用的关键字C#并[!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)]为 null。</span><span class="sxs-lookup"><span data-stu-id="86564-106">The keyword for a null reference in C# and [!INCLUDE[TLA#tla_cpp](../../../includes/tlasharptla-cpp-md.md)] is null.</span></span> <span data-ttu-id="86564-107">Null 引用的 Microsoft Visual Basic 关键字`Nothing`，但始终使用`{x:Null}`作为 XAML 使用而不考虑 XAML 与关联的隐藏代码语言。</span><span class="sxs-lookup"><span data-stu-id="86564-107">The Microsoft Visual Basic keyword for a null reference is `Nothing`, but you always use `{x:Null}` as the XAML usage regardless which code-behind language you associate with the XAML.</span></span>  
  
 <span data-ttu-id="86564-108">`x:Null`标记扩展没有任何可设置属性。</span><span class="sxs-lookup"><span data-stu-id="86564-108">The `x:Null` markup extension has no settable properties.</span></span>  
  
 <span data-ttu-id="86564-109">为 null 的使用情况通常是与 XAML 成员公开的 CLR<xref:System.Nullable%601>值。</span><span class="sxs-lookup"><span data-stu-id="86564-109">A null usage is often associated with the XAML member exposure of a CLR <xref:System.Nullable%601> value.</span></span>  
  
 <span data-ttu-id="86564-110">`x:Null`标记扩展，所有 XAML 标记扩展，如使用大括号 (`{,}`) 用于转义属性值为非文本或事件处理程序引用的处理。</span><span class="sxs-lookup"><span data-stu-id="86564-110">The `x:Null` markup extension, like all XAML markup extensions, uses the braces (`{,}`) for escaping the handling of attribute values to be other than literals or event-handler references.</span></span> <span data-ttu-id="86564-111">特性语法是最常使用此标记扩展使用的语法。</span><span class="sxs-lookup"><span data-stu-id="86564-111">Attribute syntax is the syntax most frequently used with this markup extension.</span></span> <span data-ttu-id="86564-112">对象元素语法`<x:Null />`是从技术上讲是可行的但很少使用，因为`x:Null`标记扩展不包含位置参数或构造参数。</span><span class="sxs-lookup"><span data-stu-id="86564-112">An object element syntax `<x:Null />` is technically possible, but is rarely used because the `x:Null` markup extension has no positional parameters or construction arguments.</span></span>  
  
 <span data-ttu-id="86564-113">有关标记扩展的信息，请参阅[标记扩展和 WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md)。</span><span class="sxs-lookup"><span data-stu-id="86564-113">For information about markup extensions, see [Markup Extensions and WPF XAML](../wpf/advanced/markup-extensions-and-wpf-xaml.md).</span></span>  
  
 <span data-ttu-id="86564-114">在.NET Framework XAML 服务中，对此标记扩展的处理由定义<xref:System.Windows.Markup.NullExtension>类。</span><span class="sxs-lookup"><span data-stu-id="86564-114">In .NET Framework XAML Services, the handling for this markup extension is defined by the <xref:System.Windows.Markup.NullExtension> class.</span></span>  
  
## <a name="wpf-usage-notes"></a><span data-ttu-id="86564-115">WPF 用法说明</span><span class="sxs-lookup"><span data-stu-id="86564-115">WPF Usage Notes</span></span>  
 <span data-ttu-id="86564-116">请注意，`null`不一定是引用类型依赖属性的初始取消设置的值。</span><span class="sxs-lookup"><span data-stu-id="86564-116">Note that `null` is not necessarily the initial unset value for a reference-type dependency property.</span></span> <span data-ttu-id="86564-117">初始默认值为每个依赖属性而异，并可以基于特定于属性的元数据。</span><span class="sxs-lookup"><span data-stu-id="86564-117">The initial default value can vary for each dependency property and can be based on property-specific metadata.</span></span> <span data-ttu-id="86564-118">许多依赖项属性不接受`null`值，不管是通过标记或代码由于它们的验证回调实现。</span><span class="sxs-lookup"><span data-stu-id="86564-118">Many dependency properties do not accept `null` as a value, either through markup or code because of their validation callback implementations.</span></span> <span data-ttu-id="86564-119">有关依赖项属性的详细信息，请参阅[依赖属性概述](../wpf/advanced/dependency-properties-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="86564-119">For more information about dependency properties, see [Dependency Properties Overview](../wpf/advanced/dependency-properties-overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86564-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="86564-120">See also</span></span>

- <xref:System.Windows.DependencyProperty.UnsetValue>
- [<span data-ttu-id="86564-121">XAML 概述 (WPF)</span><span class="sxs-lookup"><span data-stu-id="86564-121">XAML Overview (WPF)</span></span>](../wpf/advanced/xaml-overview-wpf.md)
- [<span data-ttu-id="86564-122">标记扩展和 WPF XAML</span><span class="sxs-lookup"><span data-stu-id="86564-122">Markup Extensions and WPF XAML</span></span>](../wpf/advanced/markup-extensions-and-wpf-xaml.md)
