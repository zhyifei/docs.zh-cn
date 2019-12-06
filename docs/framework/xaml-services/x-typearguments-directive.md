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
ms.openlocfilehash: 2e64c716ee85934bf02c016ee408b8e5f612a819
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837189"
---
# <a name="xtypearguments-directive"></a><span data-ttu-id="5a44f-102">x:TypeArguments 指令</span><span class="sxs-lookup"><span data-stu-id="5a44f-102">x:TypeArguments Directive</span></span>
<span data-ttu-id="5a44f-103">将泛型的约束类型参数传递到泛型类型的构造函数。</span><span class="sxs-lookup"><span data-stu-id="5a44f-103">Passes constraining type arguments of a generic to the constructor of the generic type.</span></span>  
  
## <a name="xaml-attribute-usage"></a><span data-ttu-id="5a44f-104">XAML 特性用法</span><span class="sxs-lookup"><span data-stu-id="5a44f-104">XAML Attribute Usage</span></span>  
  
```xaml  
<object x:TypeArguments="typeString" .../>  
```  
  
## <a name="xaml-values"></a><span data-ttu-id="5a44f-105">XAML 值</span><span class="sxs-lookup"><span data-stu-id="5a44f-105">XAML Values</span></span>  
  
|||  
|-|-|  
|`object`|<span data-ttu-id="5a44f-106">XAML 类型的对象元素声明，由 CLR 泛型类型支持。</span><span class="sxs-lookup"><span data-stu-id="5a44f-106">An object element declaration of a XAML type, which is backed by a CLR generic type.</span></span> <span data-ttu-id="5a44f-107">如果 `object` 引用的 XAML 类型不是来自默认的 XAML 命名空间，`object` 需要一个前缀来指示 `object` 存在的 XAML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="5a44f-107">If `object` refers to a XAML type that is not from the default XAML namespace, `object` requires a prefix to indicate the XAML namespace where `object` exists.</span></span>|  
|`typeString`|<span data-ttu-id="5a44f-108">一个字符串，它将一个或多个 XAML 类型名称声明为字符串，这些名称提供 CLR 泛型类型的类型参数。</span><span class="sxs-lookup"><span data-stu-id="5a44f-108">A string that declares one or more XAML type names as strings, which supplies the type arguments for the CLR generic type.</span></span> <span data-ttu-id="5a44f-109">有关其他语法说明，请参阅备注。</span><span class="sxs-lookup"><span data-stu-id="5a44f-109">See Remarks for additional syntax notes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a44f-110">备注</span><span class="sxs-lookup"><span data-stu-id="5a44f-110">Remarks</span></span>  
 <span data-ttu-id="5a44f-111">在大多数情况下，作为 `typeString` 字符串中的信息项使用的 XAML 类型作为前缀。</span><span class="sxs-lookup"><span data-stu-id="5a44f-111">In most cases, the XAML types that are used as an information item in a `typeString` string are prefixed.</span></span> <span data-ttu-id="5a44f-112">CLR 泛型约束（例如 <xref:System.Int32> 和 <xref:System.String>）的典型类型来自 CLR 基类库。</span><span class="sxs-lookup"><span data-stu-id="5a44f-112">Typical types of CLR generic constraints (for example, <xref:System.Int32> and <xref:System.String>) come from CLR base class libraries.</span></span> <span data-ttu-id="5a44f-113">这些库不会映射到典型的特定于框架的默认 XAML 命名空间，因此需要 XAML 使用的前缀映射。</span><span class="sxs-lookup"><span data-stu-id="5a44f-113">Those libraries are not mapped to typical framework-specific default XAML namespaces, and therefore, require a prefix mapping for XAML usage.</span></span>  
  
 <span data-ttu-id="5a44f-114">可以使用逗号分隔符指定多个 XAML 类型名称。</span><span class="sxs-lookup"><span data-stu-id="5a44f-114">You can specify more than one XAML type name by using a comma delimiter.</span></span>  
  
 <span data-ttu-id="5a44f-115">如果泛型约束本身使用泛型类型，则嵌套约束类型参数可以包含在括号（）中。</span><span class="sxs-lookup"><span data-stu-id="5a44f-115">If the generic constraints themselves use generic types, the nested constraint type arguments can be contained by parentheses ().</span></span>  
  
 <span data-ttu-id="5a44f-116">请注意，`x:TypeArguments` 的这一定义特定于 .NET Framework XAML 服务和使用 CLR 支持。</span><span class="sxs-lookup"><span data-stu-id="5a44f-116">Note that this definition of `x:TypeArguments` is specific to .NET Framework XAML Services and using CLR backing.</span></span> <span data-ttu-id="5a44f-117">可以在[\[的 MS-XAML\] 部分](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10))中找到语言级定义5.3.11。</span><span class="sxs-lookup"><span data-stu-id="5a44f-117">A language-level definition can be found in [\[MS-XAML\] Section 5.3.11](https://docs.microsoft.com/previous-versions/msp-n-p/ff650760(v=pandp.10)).</span></span>  
  
## <a name="usage-examples"></a><span data-ttu-id="5a44f-118">用法示例</span><span class="sxs-lookup"><span data-stu-id="5a44f-118">Usage Examples</span></span>  
 <span data-ttu-id="5a44f-119">对于这些示例，假定声明以下 XAML 命名空间定义：</span><span class="sxs-lookup"><span data-stu-id="5a44f-119">For these examples, assume that the following XAML namespace definitions are declared:</span></span>  
  
```xaml  
xmlns:sys="clr-namespace:System;assembly=mscorlib"  
xmlns:scg="clr-namespace:System.Collections.Generic;assembly=mscorlib"  
```  
  
### <a name="liststring"></a><span data-ttu-id="5a44f-120">列出\<字符串 ></span><span class="sxs-lookup"><span data-stu-id="5a44f-120">List\<String></span></span>  
 <span data-ttu-id="5a44f-121">`<scg:List x:TypeArguments="sys:String" ...>` 使用 <xref:System.String> 类型参数实例化新的 <xref:System.Collections.Generic.List%601>。</span><span class="sxs-lookup"><span data-stu-id="5a44f-121">`<scg:List x:TypeArguments="sys:String" ...>` instantiates a new <xref:System.Collections.Generic.List%601> with a <xref:System.String> type argument.</span></span>  
  
### <a name="dictionarystringstring"></a><span data-ttu-id="5a44f-122">Dictionary\<String，String ></span><span class="sxs-lookup"><span data-stu-id="5a44f-122">Dictionary\<String,String></span></span>  
 <span data-ttu-id="5a44f-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` 使用两个 <xref:System.String> 类型参数实例化新的 <xref:System.Collections.Generic.Dictionary%602>。</span><span class="sxs-lookup"><span data-stu-id="5a44f-123">`<scg:Dictionary x:TypeArguments="sys:String,sys:String" ...>` instantiates a new <xref:System.Collections.Generic.Dictionary%602> with two <xref:System.String> type arguments.</span></span>  
  
### <a name="queuekeyvaluepairstringstring"></a><span data-ttu-id="5a44f-124">队列 < KeyValuePair\<String，String > ></span><span class="sxs-lookup"><span data-stu-id="5a44f-124">Queue<KeyValuePair\<String,String>></span></span>  
 <span data-ttu-id="5a44f-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` 实例化一个新的 <xref:System.Collections.Generic.Queue%601>，它具有与内部约束类型参数 <xref:System.String> 和 <xref:System.String>的 <xref:System.Collections.Generic.KeyValuePair%602> 约束。</span><span class="sxs-lookup"><span data-stu-id="5a44f-125">`<scg:Queue x:TypeArguments="scg:KeyValuePair(sys:String,sys:String)" ...>` instantiates a new <xref:System.Collections.Generic.Queue%601> that has a constraint of <xref:System.Collections.Generic.KeyValuePair%602> with the inner constraint type arguments <xref:System.String> and <xref:System.String>.</span></span>  
  
## <a name="xaml-2006-and-wpf-generic-xaml-usages"></a><span data-ttu-id="5a44f-126">XAML 2006 和 WPF 泛型 XAML 用法</span><span class="sxs-lookup"><span data-stu-id="5a44f-126">XAML 2006 and WPF Generic XAML Usages</span></span>  
 <span data-ttu-id="5a44f-127">对于 XAML 2006 用法以及用于 WPF 应用程序的 XAML，一般情况下，XAML 中的 `x:TypeArguments` 和泛型类型用法存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="5a44f-127">For XAML 2006 usage, and XAML that is used for WPF applications, the following restrictions exist for `x:TypeArguments` and generic type usages from XAML in general:</span></span>  
  
- <span data-ttu-id="5a44f-128">只有 XAML 文件的根元素可以支持引用泛型类型的泛型 XAML 用法。</span><span class="sxs-lookup"><span data-stu-id="5a44f-128">Only the root element of a XAML file can support a generic XAML usage that references a generic type.</span></span>  
  
- <span data-ttu-id="5a44f-129">根元素必须映射到至少具有一个类型参数的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="5a44f-129">The root element must map to a generic type with at least one type argument.</span></span> <span data-ttu-id="5a44f-130">示例为 <xref:System.Windows.Navigation.PageFunction%601>。</span><span class="sxs-lookup"><span data-stu-id="5a44f-130">An example is <xref:System.Windows.Navigation.PageFunction%601>.</span></span> <span data-ttu-id="5a44f-131">页函数是 WPF 中 XAML 泛型用法支持的主要方案。</span><span class="sxs-lookup"><span data-stu-id="5a44f-131">The page functions are the primary scenario for XAML generic usage support in WPF.</span></span>  
  
- <span data-ttu-id="5a44f-132">泛型的根元素 XAML 对象元素还必须使用 `x:Class`声明分部类。</span><span class="sxs-lookup"><span data-stu-id="5a44f-132">The root element XAML object element for the generic must also declare a partial class using `x:Class`.</span></span> <span data-ttu-id="5a44f-133">即使定义 WPF 生成操作也是如此。</span><span class="sxs-lookup"><span data-stu-id="5a44f-133">This is true even if defining a WPF build action.</span></span>  
  
- <span data-ttu-id="5a44f-134">`x:TypeArguments` 无法引用嵌套的泛型约束。</span><span class="sxs-lookup"><span data-stu-id="5a44f-134">`x:TypeArguments` cannot reference nested generic constraints.</span></span>  
  
## <a name="xaml-2009-or-xaml-2006-with-no-wpf-30-or-wpf-35-dependency"></a><span data-ttu-id="5a44f-135">不带 WPF 3.0 或 WPF 3.5 依赖项的 XAML 2009 或 XAML 2006</span><span class="sxs-lookup"><span data-stu-id="5a44f-135">XAML 2009 or XAML 2006 with No WPF 3.0 or WPF 3.5 Dependency</span></span>  
 <span data-ttu-id="5a44f-136">在 XAML 2006 或 XAML 2009 .NET Framework XAML 服务中，对泛型 XAML 用法的 WPF 相关限制是宽松的。</span><span class="sxs-lookup"><span data-stu-id="5a44f-136">In .NET Framework XAML Services for either XAML 2006 or XAML 2009, the WPF-related restrictions on generic XAML usage are relaxed.</span></span> <span data-ttu-id="5a44f-137">可以在支持类型系统和对象模型可以支持的 XAML 标记中的任意位置实例化泛型对象元素。</span><span class="sxs-lookup"><span data-stu-id="5a44f-137">You can instantiate a generic object element at any position in XAML markup that the backing type system and object model can support.</span></span>  
  
 <span data-ttu-id="5a44f-138">如果使用 XAML 2009，而不是映射 CLR 基类型以获取公共语言基元的 XAML 类型，则可以将[常见 XAML 语言基元的内置类型](built-in-types-for-common-xaml-language-primitives.md)用作 `typeString`中的信息项。</span><span class="sxs-lookup"><span data-stu-id="5a44f-138">If you use XAML 2009 instead of mapping the CLR base types to obtain XAML types for common language primitives, you can use [Built-in Types for Common XAML Language Primitives](built-in-types-for-common-xaml-language-primitives.md) as information items in a `typeString`.</span></span> <span data-ttu-id="5a44f-139">例如，可以声明以下内容（前缀映射未显示，但 x 是 xaml 2009 的 xaml 语言命名空间）：</span><span class="sxs-lookup"><span data-stu-id="5a44f-139">For example, you could declare the following (prefix mappings not shown, but x is the XAML language XAML namespace for XAML 2009):</span></span>  
  
```xaml  
<my:BusinessObject x:TypeArguments="x:String,x:Int32"/>  
```  
  
 <span data-ttu-id="5a44f-140">在 WPF 中，在面向 .NET Framework 4 时，可以将 XAML 2009 功能与 `x:TypeArguments` 一起使用，但仅适用于松散 XAML （非标记编译的 XAML）。</span><span class="sxs-lookup"><span data-stu-id="5a44f-140">In WPF and when targeting .NET Framework 4, you can use XAML 2009 features together with `x:TypeArguments` but only for loose XAML (XAML that is not markup-compiled).</span></span> <span data-ttu-id="5a44f-141">WPF 的已编译标记的 XAML 以及 XAML 的 BAML 形式当前不支持 XAML 2009 关键字和功能。</span><span class="sxs-lookup"><span data-stu-id="5a44f-141">Markup-compiled XAML for WPF and the BAML form of XAML do not currently support the XAML 2009 keywords and features.</span></span> <span data-ttu-id="5a44f-142">如果需要对 XAML 进行标记编译，则必须在 "XAML 2006 和 WPF 一般 XAML 用法" 一节中所述的限制下运行。</span><span class="sxs-lookup"><span data-stu-id="5a44f-142">If you need to markup compile the XAML, you must operate under the restrictions noted in the "XAML 2006 and WPF Generic XAML Usages" section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a44f-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a44f-143">See also</span></span>

- [<span data-ttu-id="5a44f-144">x:Class 指令</span><span class="sxs-lookup"><span data-stu-id="5a44f-144">x:Class Directive</span></span>](x-class-directive.md)
- [<span data-ttu-id="5a44f-145">x:Type 标记扩展</span><span class="sxs-lookup"><span data-stu-id="5a44f-145">x:Type Markup Extension</span></span>](x-type-markup-extension.md)
- [<span data-ttu-id="5a44f-146">常见 XAML 语言基元的内置类型</span><span class="sxs-lookup"><span data-stu-id="5a44f-146">Built-in Types for Common XAML Language Primitives</span></span>](built-in-types-for-common-xaml-language-primitives.md)
- [<span data-ttu-id="5a44f-147">XAML 中的泛型</span><span class="sxs-lookup"><span data-stu-id="5a44f-147">Generics in XAML</span></span>](generics-in-xaml.md)
