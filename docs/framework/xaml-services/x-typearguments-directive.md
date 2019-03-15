---
title: x:TypeArguments 指令
ms.date: 03/30/2017
f1_keywords:
- x:TypeArguments
- xTypeArguments
- TypeArguments
helpviewer_keywords:
- x:TypeArguments attribute [XAML Services]
- TypeArguments attribute in XAML [XAML Services]
- XAML [XAML Services], x:TypeArguments attribute
ms.assetid: 86561058-d393-4a44-b5c3-993a4513ea74
ms.openlocfilehash: 0d3edf6c7a16fc206832d8d6deff9d4ac2f69ba3
ms.sourcegitcommit: 5c1abeec15fbddcc7dbaa729fabc1f1f29f12045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "58043272"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="12db8-102">x:TypeArguments 指令</span><span class="sxs-lookup"><span data-stu-id="12db8-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="12db8-103">约束类型参数传递给泛型类型的构造函数的泛型。</span><span class="sxs-lookup"><span data-stu-id="12db8-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="12db8-104">XAML 属性用法</span><span class="sxs-lookup"><span data-stu-id="12db8-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="12db8-105">XAML 值</span><span class="sxs-lookup"><span data-stu-id="12db8-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="12db8-106">由 CLR 泛型类型提供支持的 XAML 类型的对象元素声明。</span><span class="sxs-lookup"><span data-stu-id="12db8-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="12db8-107">如果`object`不是默认 XAML 命名空间中的 XAML 类型是指`object`需要一个指示 XAML 命名空间前缀其中`object`存在。</span><span class="sxs-lookup"><span data-stu-id="12db8-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="12db8-108">一个字符串，声明一个或多个 XAML 类型名称以字符串形式提供的类型参数的 CLR 泛型类型。</span><span class="sxs-lookup"><span data-stu-id="12db8-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="12db8-109">有关其他语法说明，请参阅备注。</span><span class="sxs-lookup"><span data-stu-id="12db8-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12db8-110">备注</span><span class="sxs-lookup"><span data-stu-id="12db8-110">Remarks</span></span>  
 <span data-ttu-id="12db8-111">在大多数情况下，为信息项中使用的 XAML 类型`typeString`字符串作为前缀。</span><span class="sxs-lookup"><span data-stu-id="12db8-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="12db8-112">典型类型的 CLR 的泛型约束 (例如，<xref:System.Int32>和<xref:System.String>) 来自 CLR 基类库。</span><span class="sxs-lookup"><span data-stu-id="12db8-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="12db8-113">这些库不映射到典型的特定于框架的默认 XAML 命名空间，因此，对于 XAML 使用情况需要前缀映射。</span><span class="sxs-lookup"><span data-stu-id="12db8-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="12db8-114">可以通过使用逗号分隔符指定多个 XAML 类型名称。</span><span class="sxs-lookup"><span data-stu-id="12db8-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="12db8-115">如果泛型约束自身使用的泛型类型，括号 （） 可以包含嵌套的约束类型参数。</span><span class="sxs-lookup"><span data-stu-id="12db8-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="12db8-116">请注意，此定义的`x:TypeArguments`是特定于.NET Framework XAML 服务和使用 CLR 支持。</span><span class="sxs-lookup"><span data-stu-id="12db8-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="12db8-117">可以在中找到的语言级别定义[ \[MS XAML\]部分 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525)。</span><span class="sxs-lookup"><span data-stu-id="12db8-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://go.microsoft.com/fwlink/?LinkId=114525).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="12db8-118">用法示例</span><span class="sxs-lookup"><span data-stu-id="12db8-118">Usage Examples</span></span>  
 <span data-ttu-id="12db8-119">对于这些示例，假定声明以下 XAML 命名空间定义：</span><span class="sxs-lookup"><span data-stu-id="12db8-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="12db8-120">列表\<字符串 ></span><span class="sxs-lookup"><span data-stu-id="12db8-120">List\<String></span></span>  
 <span data-ttu-id="12db8-121">`<scg:List x:TypeArguments="sys:String" ...>` 实例化新<xref:System.Collections.Generic.List%601>与<xref:System.String>类型实参。</span><span class="sxs-lookup"><span data-stu-id="12db8-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="12db8-122">字典\<字符串、 字符串 ></span><span class="sxs-lookup"><span data-stu-id="12db8-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="12db8-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` 实例化新<xref:System.Collections.Generic.Dictionary%602>具有两个<xref:System.String>类型参数。</span><span class="sxs-lookup"><span data-stu-id="12db8-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="12db8-124">队列 < KeyValuePair\<String，String >></span><span class="sxs-lookup"><span data-stu-id="12db8-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="12db8-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` 实例化新<xref:System.Collections.Generic.Queue%601>具有的约束<xref:System.Collections.Generic.KeyValuePair%602>内部约束类型参数与<xref:System.String>和<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="12db8-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="12db8-126">XAML 2006 和 WPF 泛型 XAML 用法</span><span class="sxs-lookup"><span data-stu-id="12db8-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="12db8-127">有关 XAML 2006 使用情况和 XAML 的 WPF 应用程序使用，存在以下限制`x:TypeArguments`和从 XAML 中常规的泛型类型用法：</span><span class="sxs-lookup"><span data-stu-id="12db8-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
-   <span data-ttu-id="12db8-128">XAML 文件的根元素可以支持引用泛型类型的泛型 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="12db8-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
-   <span data-ttu-id="12db8-129">根元素必须映射到具有至少一个类型参数的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="12db8-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="12db8-130">例如， <xref:System.Windows.Navigation.PageFunction%601>。</span><span class="sxs-lookup"><span data-stu-id="12db8-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="12db8-131">页函数是 XAML 在 WPF 中的泛型用法支持的主要方案。</span><span class="sxs-lookup"><span data-stu-id="12db8-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
-   <span data-ttu-id="12db8-132">泛型的根元素 XAML 对象元素还必须声明分部类使用`x:Class`。</span><span class="sxs-lookup"><span data-stu-id="12db8-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="12db8-133">即使定义 WPF 生成操作，这是如此。</span><span class="sxs-lookup"><span data-stu-id="12db8-133">This is true even if defining a WPF build action.</span></span>  
  
-   <span data-ttu-id="12db8-134">`x:TypeArguments` 不能引用嵌套的泛型约束。</span><span class="sxs-lookup"><span data-stu-id="12db8-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="12db8-135">XAML 2009 或不带任何 WPF 3.0 或 3.5 WPF XAML 2006 依赖关系</span><span class="sxs-lookup"><span data-stu-id="12db8-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="12db8-136">在.NET Framework XAML 服务 XAML 2006 或 XAML 2009，放宽了对泛型的 XAML 用法的 WPF 相关限制。</span><span class="sxs-lookup"><span data-stu-id="12db8-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="12db8-137">您可以实例化泛型对象元素，在后备类型系统和对象模型可以支持的 XAML 标记中的任意位置。</span><span class="sxs-lookup"><span data-stu-id="12db8-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="12db8-138">如果使用 XAML 2009 而不是将 CLR 映射基类型来获取常用语言基元的 XAML 类型转换，则可以使用[常见 XAML 语言基元的内置类型](built-in-types-for-common-xaml-language-primitives.md)中的信息项作为`typeString`。</span><span class="sxs-lookup"><span data-stu-id="12db8-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="12db8-139">例如，您可以声明以下 （前缀映射不显示，但 x 是 XAML 2009 的 XAML 语言 XAML 命名空间）：</span><span class="sxs-lookup"><span data-stu-id="12db8-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="12db8-140">在 WPF 中并面向[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，可以使用 XAML 2009 功能一起使用`x:TypeArguments`但只针对松散 XAML (未标记编译的 XAML)。</span><span class="sxs-lookup"><span data-stu-id="12db8-140">In WPF and when targeting [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="12db8-141">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="12db8-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="12db8-142">如果需要为标记编译 XAML，您必须在"XAML 2006 和 WPF 泛型 XAML 用法"部分中所述的限制下进行操作。</span><span class="sxs-lookup"><span data-stu-id="12db8-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12db8-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="12db8-143">See also</span></span>
- [<span data-ttu-id="12db8-144">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="12db8-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="12db8-145">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="12db8-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="12db8-146">常见 XAML 语言基元的内置类型</span><span class="sxs-lookup"><span data-stu-id="12db8-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="12db8-147">XAML 中的泛型</span><span class="sxs-lookup"><span data-stu-id="12db8-147">Generics in XAML</span></span>](generics-in-xaml.md)
