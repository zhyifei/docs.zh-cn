---
title: x:Reference 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: f06e259893111a436e5afe2df754c3edee326d54
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432652"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="e2e0e-102">x:Reference 标记扩展</span><span class="sxs-lookup"><span data-stu-id="e2e0e-102">x:Reference Markup Extension</span></span>

<span data-ttu-id="e2e0e-103">引用在 XAML 标记中其他位置声明的实例。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="e2e0e-104">引用引用元素的`x:Name`。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-104">The reference refers to an element's `x:Name`.</span></span>

## <a name="xaml-attribute-usage"></a><span data-ttu-id="e2e0e-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="e2e0e-105">XAML Attribute Usage</span></span>

```xaml
<object property="{x:Reference instancexName}" .../>
```

## <a name="xaml-object-element-usage"></a><span data-ttu-id="e2e0e-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="e2e0e-106">XAML Object Element Usage</span></span>

```xaml
<object>
  <object.property>
    <x:Reference Name="instancexName"/>
  </object.property>
</object>
```

## <a name="xaml-values"></a><span data-ttu-id="e2e0e-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="e2e0e-107">XAML Values</span></span>

|||
|-|-|
|`instancexName`|<span data-ttu-id="e2e0e-108">引用`x:Name`实例的值（或<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-标识属性的值）。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|

## <a name="remarks"></a><span data-ttu-id="e2e0e-109">备注</span><span class="sxs-lookup"><span data-stu-id="e2e0e-109">Remarks</span></span>

<span data-ttu-id="e2e0e-110">`x:Reference`为元素引用概念提供 XAML 语言级别支持，该概念在 WPF 等特定框架中以其他方式实现。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>

## <a name="xreference-and-wpf"></a><span data-ttu-id="e2e0e-111">x：参考和WPF</span><span class="sxs-lookup"><span data-stu-id="e2e0e-111">x:Reference and WPF</span></span>

<span data-ttu-id="e2e0e-112">在 WPF 和 XAML 2006 中，元素引用由绑定的框架<xref:System.Windows.Data.Binding.ElementName%2A>级功能解决。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="e2e0e-113">对于大多数 WPF 应用程序和方案，<xref:System.Windows.Data.Binding.ElementName%2A>仍应使用绑定。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="e2e0e-114">此一般指南的例外情况可能包括存在数据上下文或其他范围范围注意事项，使数据绑定不切实际，并且不涉及标记编译的情况。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>

<span data-ttu-id="e2e0e-115">`x:Reference`是在 XAML 2009 中定义的构造。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="e2e0e-116">在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行 WPF 标记编译的 XAML。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="e2e0e-117">标记编译的 XAML 以及 BAML 形式的 XAML 当前不支持 XAML 2009 语言关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="e2e0e-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
