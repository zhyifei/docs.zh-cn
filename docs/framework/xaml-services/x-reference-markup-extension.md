---
title: x:Reference 标记扩展
ms.date: 03/30/2017
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
ms.openlocfilehash: 960f5c0e4192df72090c1a571dfc2fc5e3fd8ba3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938874"
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="57a02-102">x:Reference 标记扩展</span><span class="sxs-lookup"><span data-stu-id="57a02-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="57a02-103">在 XAML 标记中其他地方声明的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="57a02-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="57a02-104">引用所引用的元素的`x:Name`。</span><span class="sxs-lookup"><span data-stu-id="57a02-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="57a02-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="57a02-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="57a02-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="57a02-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="57a02-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="57a02-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="57a02-108">`x:Name`值 (或值<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-标识属性) 的引用的实例。</span><span class="sxs-lookup"><span data-stu-id="57a02-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57a02-109">备注</span><span class="sxs-lookup"><span data-stu-id="57a02-109">Remarks</span></span>  
 <span data-ttu-id="57a02-110">`x:Reference` 提供对一个元素的引用概念，否则在特定框架，如 WPF 中实现 XAML 语言级别支持。</span><span class="sxs-lookup"><span data-stu-id="57a02-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="57a02-111">x： 引用和 WPF</span><span class="sxs-lookup"><span data-stu-id="57a02-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="57a02-112">在 WPF 和 XAML 2006 中，元素的引用进行寻址的框架级别功能<xref:System.Windows.Data.Binding.ElementName%2A>绑定。</span><span class="sxs-lookup"><span data-stu-id="57a02-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="57a02-113">对于大多数 WPF 应用程序和方案，<xref:System.Windows.Data.Binding.ElementName%2A>应仍使用绑定。</span><span class="sxs-lookup"><span data-stu-id="57a02-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="57a02-114">此一般指南的例外情况可能包括用例，其中没有数据上下文或使数据绑定无法实际应用其他作用域注意事项，且不涉及标记编译。</span><span class="sxs-lookup"><span data-stu-id="57a02-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="57a02-115">`x:Reference` 一种构造是在 XAML 2009 中定义。</span><span class="sxs-lookup"><span data-stu-id="57a02-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="57a02-116">在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行 WPF 标记编译的 XAML。</span><span class="sxs-lookup"><span data-stu-id="57a02-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="57a02-117">标记编译的 XAML 以及 BAML 形式的 XAML 当前不支持 XAML 2009 语言关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="57a02-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
