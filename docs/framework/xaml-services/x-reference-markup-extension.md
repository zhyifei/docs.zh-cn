---
title: "x:Reference 标记扩展"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- x:Reference markup extension [XAML Services]
- XAML [XAML Services], x:Reference Markup Extension
- Reference markup extension [XAML Services]
ms.assetid: 2982e68b-d26b-4aa3-826a-34c57a9c5199
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03b63cb40e57223d5c66c03fb60780689cd6c925
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="xreference-markup-extension"></a><span data-ttu-id="9c56e-102">x:Reference 标记扩展</span><span class="sxs-lookup"><span data-stu-id="9c56e-102">x:Reference Markup Extension</span></span>
<span data-ttu-id="9c56e-103">在 XAML 标记中其他位置声明的实例的引用。</span><span class="sxs-lookup"><span data-stu-id="9c56e-103">References an instance that is declared elsewhere in XAML markup.</span></span> <span data-ttu-id="9c56e-104">引用所引用的元素`x:Name`。</span><span class="sxs-lookup"><span data-stu-id="9c56e-104">The reference refers to an element's `x:Name`.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="9c56e-105">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="9c56e-105">XAML Attribute Usage</span></span>  
  
```xaml  
<object property="{x:Reference instancexName}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a><span data-ttu-id="9c56e-106">XAML 对象元素用法</span><span class="sxs-lookup"><span data-stu-id="9c56e-106">XAML Object Element Usage</span></span>  
  
```xaml  
<object>  
  <object.property>  
    <x:Reference Name="instancexName"/>  
  </object.property>  
</object>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="9c56e-107">XAML 值</span><span class="sxs-lookup"><span data-stu-id="9c56e-107">XAML Values</span></span>  
  
|||  
|-|-|  
|`instancexName`|<span data-ttu-id="9c56e-108">`x:Name`值 (或值<xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-标识属性) 的引用的实例。</span><span class="sxs-lookup"><span data-stu-id="9c56e-108">The `x:Name` value (or value of the <xref:System.Windows.Markup.RuntimeNamePropertyAttribute>-identified property) of the referenced instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9c56e-109">备注</span><span class="sxs-lookup"><span data-stu-id="9c56e-109">Remarks</span></span>  
 <span data-ttu-id="9c56e-110">`x:Reference`提供对否则在特定的框架，例如 WPF 中实现的一个元素引用概念 XAML 语言级别支持。</span><span class="sxs-lookup"><span data-stu-id="9c56e-110">`x:Reference` provides XAML language-level support for an element reference concept that was otherwise implemented in specific frameworks such as WPF.</span></span>  
  
## <a name="xreference-and-wpf"></a><span data-ttu-id="9c56e-111">X:reference 和 WPF</span><span class="sxs-lookup"><span data-stu-id="9c56e-111">x:Reference and WPF</span></span>  
 <span data-ttu-id="9c56e-112">在 WPF 和 XAML 2006 中，元素引用都由框架级别功能的<xref:System.Windows.Data.Binding.ElementName%2A>绑定。</span><span class="sxs-lookup"><span data-stu-id="9c56e-112">In WPF and XAML 2006, element references are addressed by the framework-level feature of <xref:System.Windows.Data.Binding.ElementName%2A> binding.</span></span> <span data-ttu-id="9c56e-113">对于大多数 WPF 应用程序和方案，<xref:System.Windows.Data.Binding.ElementName%2A>应仍使用绑定。</span><span class="sxs-lookup"><span data-stu-id="9c56e-113">For most WPF applications and scenarios, <xref:System.Windows.Data.Binding.ElementName%2A> binding should still be used.</span></span> <span data-ttu-id="9c56e-114">此一般性指导异常可能包含情况下，有数据上下文或使数据绑定显得不切实际其他作用域注意事项以及标记编译不涉及到在其中。</span><span class="sxs-lookup"><span data-stu-id="9c56e-114">Exceptions to this general guidance might include cases where there are data context or other scoping considerations that make data binding impractical and where markup compilation is not involved.</span></span>  
  
 <span data-ttu-id="9c56e-115">`x:Reference`在 XAML 2009 中定义一个构造。</span><span class="sxs-lookup"><span data-stu-id="9c56e-115">`x:Reference` is a construct defined in XAML 2009.</span></span> <span data-ttu-id="9c56e-116">在 WPF 中，可以使用 XAML 2009 功能，但仅针对未进行 WPF 标记编译的 XAML。</span><span class="sxs-lookup"><span data-stu-id="9c56e-116">In WPF, you can use XAML 2009 features, but only for XAML that is not WPF markup-compiled.</span></span> <span data-ttu-id="9c56e-117">标记编译的 XAML 以及 BAML 形式的 XAML 当前不支持 XAML 2009 语言关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="9c56e-117">Markup-compiled XAML and the BAML form of XAML do not currently support the XAML 2009 language keywords and features.</span></span>
