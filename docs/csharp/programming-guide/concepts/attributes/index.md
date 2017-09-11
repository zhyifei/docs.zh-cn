---
title: "特性 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f148f13f-a0d5-4f22-9c87-4b73d5dde270
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: ab55021a073f914905e29163ba2a669f69d6dcab
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="attributes-c"></a><span data-ttu-id="3a980-102">特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a980-102">Attributes (C#)</span></span>
<span data-ttu-id="3a980-103">使用特性，可以有效地将元数据或声明性信息与代码（程序集、类型、方法、属性等）相关联。</span><span class="sxs-lookup"><span data-stu-id="3a980-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="3a980-104">将特性与程序实体相关联后，可以在运行时使用*反射*这项技术查询特性。</span><span class="sxs-lookup"><span data-stu-id="3a980-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="3a980-105">有关详细信息，请参阅[反射 (C#)](../../../../csharp/programming-guide/concepts/reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="3a980-105">For more information, see [Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="3a980-106">特性具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="3a980-106">Attributes have the following properties:</span></span>  
  
-   <span data-ttu-id="3a980-107">特性向程序添加元数据。</span><span class="sxs-lookup"><span data-stu-id="3a980-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="3a980-108">*元数据*是程序中定义的类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3a980-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="3a980-109">所有 .NET 程序集都包含一组指定的元数据，用于描述程序集中定义的类型和类型成员。</span><span class="sxs-lookup"><span data-stu-id="3a980-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="3a980-110">可以添加自定义特性来指定所需的其他任何信息。</span><span class="sxs-lookup"><span data-stu-id="3a980-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="3a980-111">有关详细信息，请参阅[创建自定义特性 (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="3a980-111">For more information, see, [Creating Custom Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
-   <span data-ttu-id="3a980-112">可以将一个或多个特性应用于整个程序集、模块或较小的程序元素（如类和属性）。</span><span class="sxs-lookup"><span data-stu-id="3a980-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
-   <span data-ttu-id="3a980-113">特性可以像方法和属性一样接受自变量。</span><span class="sxs-lookup"><span data-stu-id="3a980-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
-   <span data-ttu-id="3a980-114">程序可使用反射来检查自己的元数据或其他程序中的元数据。</span><span class="sxs-lookup"><span data-stu-id="3a980-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="3a980-115">有关详细信息，请参阅[使用反射访问特性 (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)。</span><span class="sxs-lookup"><span data-stu-id="3a980-115">For more information, see [Accessing Attributes by Using Reflection (C#)](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="3a980-116">使用属性</span><span class="sxs-lookup"><span data-stu-id="3a980-116">Using Attributes</span></span>  
 <span data-ttu-id="3a980-117">可以将特性附加到大多数的声明中，尽管特定特性可能会限制可有效附加到的声明的类型。</span><span class="sxs-lookup"><span data-stu-id="3a980-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="3a980-118">在 C# 中，通过用方括号 ([]) 将特性名称括起来，并置于应用该特性的实体的声明上方以指定特性。</span><span class="sxs-lookup"><span data-stu-id="3a980-118">In C#, you specify an attribute by placing the name of the attribute, enclosed in square brackets ([]), above the declaration of the entity to which it applies.</span></span>  
  
 <span data-ttu-id="3a980-119">在此示例中，<xref:System.SerializableAttribute> 特性用于将具体特征应用于类：</span><span class="sxs-lookup"><span data-stu-id="3a980-119">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```csharp  
[System.Serializable]  
public class SampleClass  
{  
    // Objects of this type can be serialized.  
}  
```  
  
 <span data-ttu-id="3a980-120">下方声明了一个具有特性 <xref:System.Runtime.InteropServices.DllImportAttribute> 的方法：</span><span class="sxs-lookup"><span data-stu-id="3a980-120">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
[System.Runtime.InteropServices.DllImport("user32.dll")]  
extern static void SampleMethod();  
```  
  
 <span data-ttu-id="3a980-121">可以将多个特性附加到声明中：</span><span class="sxs-lookup"><span data-stu-id="3a980-121">More than one attribute can be placed on a declaration:</span></span>  
  
```csharp  
using System.Runtime.InteropServices;  
```  
  
```csharp  
void MethodA([In][Out] ref double x) { }  
void MethodB([Out][In] ref double x) { }  
void MethodC([In, Out] ref double x) { }  
```  
  
 <span data-ttu-id="3a980-122">对于给定实体，一些特性可以指定多次。</span><span class="sxs-lookup"><span data-stu-id="3a980-122">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="3a980-123"><xref:System.Diagnostics.ConditionalAttribute> 便属于此类多用途特性：</span><span class="sxs-lookup"><span data-stu-id="3a980-123">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```csharp  
[Conditional("DEBUG"), Conditional("TEST1")]  
void TraceMethod()  
{  
    // ...  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="3a980-124">按照约定，所有特性名称均以“Attribute”一词结尾，以便与 .NET Framework 中的其他项区分开来。</span><span class="sxs-lookup"><span data-stu-id="3a980-124">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="3a980-125">不过，在代码中使用特性时，无需指定特性后缀。</span><span class="sxs-lookup"><span data-stu-id="3a980-125">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="3a980-126">例如，`[DllImport]` 等同于 `[DllImportAttribute]`，但 `DllImportAttribute` 是此特性在 .NET Framework 中的实际名称。</span><span class="sxs-lookup"><span data-stu-id="3a980-126">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="3a980-127">特性参数</span><span class="sxs-lookup"><span data-stu-id="3a980-127">Attribute Parameters</span></span>  
 <span data-ttu-id="3a980-128">许多属性都有参数，可以是位置参数、未命名参数或已命名参数。</span><span class="sxs-lookup"><span data-stu-id="3a980-128">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="3a980-129">所有位置参数都必须按特定的顺序指定，不能省略；已命名参数是可选的，可以按任意顺序指定。</span><span class="sxs-lookup"><span data-stu-id="3a980-129">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="3a980-130">首先指定的是位置参数。</span><span class="sxs-lookup"><span data-stu-id="3a980-130">Positional parameters are specified first.</span></span> <span data-ttu-id="3a980-131">例如，下面这三个特性是等同的：</span><span class="sxs-lookup"><span data-stu-id="3a980-131">For example, these three attributes are equivalent:</span></span>  
  
```csharp  
[DllImport("user32.dll")]  
[DllImport("user32.dll", SetLastError=false, ExactSpelling=false)]  
[DllImport("user32.dll", ExactSpelling=false, SetLastError=false)]  
```  
  
 <span data-ttu-id="3a980-132">第一个参数（DLL 名称）是位置参数，始终第一个出现；其他是已命名参数。</span><span class="sxs-lookup"><span data-stu-id="3a980-132">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="3a980-133">在此示例中，两个已命名参数的默认值均为 false，因此可以省略。</span><span class="sxs-lookup"><span data-stu-id="3a980-133">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="3a980-134">若要了解默认参数值，请参阅各个特性文档。</span><span class="sxs-lookup"><span data-stu-id="3a980-134">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="3a980-135">特性目标</span><span class="sxs-lookup"><span data-stu-id="3a980-135">Attribute Targets</span></span>  
 <span data-ttu-id="3a980-136">特性的*目标*是指应用特性的实体。</span><span class="sxs-lookup"><span data-stu-id="3a980-136">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="3a980-137">例如，特性可应用于类、特定方法或整个程序集。</span><span class="sxs-lookup"><span data-stu-id="3a980-137">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="3a980-138">默认情况下，特性应用于它后面紧接着的元素。</span><span class="sxs-lookup"><span data-stu-id="3a980-138">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="3a980-139">不过，还可以进行显式标识。例如，可以标识为将特性应用于方法，还是应用于其参数或返回值。</span><span class="sxs-lookup"><span data-stu-id="3a980-139">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="3a980-140">若要显式标识特性目标，请使用以下语法：</span><span class="sxs-lookup"><span data-stu-id="3a980-140">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```csharp  
[target : attribute-list]  
```  
  
 <span data-ttu-id="3a980-141">下表列出了可能的 `target` 值。</span><span class="sxs-lookup"><span data-stu-id="3a980-141">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="3a980-142">目标值</span><span class="sxs-lookup"><span data-stu-id="3a980-142">Target value</span></span>|<span data-ttu-id="3a980-143">适用对象</span><span class="sxs-lookup"><span data-stu-id="3a980-143">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="3a980-144">整个程序集</span><span class="sxs-lookup"><span data-stu-id="3a980-144">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="3a980-145">当前程序集模块</span><span class="sxs-lookup"><span data-stu-id="3a980-145">Current assembly module</span></span>|  
|`field`|<span data-ttu-id="3a980-146">类或结构中的字段</span><span class="sxs-lookup"><span data-stu-id="3a980-146">Field in a class or a struct</span></span>|  
|`event`|<span data-ttu-id="3a980-147">事件</span><span class="sxs-lookup"><span data-stu-id="3a980-147">Event</span></span>|  
|`method`|<span data-ttu-id="3a980-148">方法或 `get` 和 `set` 属性访问器</span><span class="sxs-lookup"><span data-stu-id="3a980-148">Method or `get` and `set` property accessors</span></span>|  
|`param`|<span data-ttu-id="3a980-149">方法参数或 `set` 属性访问器参数</span><span class="sxs-lookup"><span data-stu-id="3a980-149">Method parameters or `set` property accessor parameters</span></span>|  
|`property`|<span data-ttu-id="3a980-150">属性</span><span class="sxs-lookup"><span data-stu-id="3a980-150">Property</span></span>|  
|`return`|<span data-ttu-id="3a980-151">方法、属性索引器或 `get` 属性访问器的返回值</span><span class="sxs-lookup"><span data-stu-id="3a980-151">Return value of a method, property indexer, or `get` property accessor</span></span>|  
|`type`|<span data-ttu-id="3a980-152">结构、类、接口、枚举或委托</span><span class="sxs-lookup"><span data-stu-id="3a980-152">Struct, class, interface, enum, or delegate</span></span>|  
  
 <span data-ttu-id="3a980-153">下面的示例展示了如何将特性应用于程序集和模块。</span><span class="sxs-lookup"><span data-stu-id="3a980-153">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="3a980-154">有关详细信息，请参阅[通用特性 (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="3a980-154">For more information, see [Common Attributes (C#)](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```csharp  
using System;  
using System.Reflection;  
[assembly: AssemblyTitleAttribute("Production assembly 4")]  
[module: CLSCompliant(true)]  
```  
  
 <span data-ttu-id="3a980-155">以下示例演示如何将特性应用于 C# 中的方法、方法参数和方法返回值。</span><span class="sxs-lookup"><span data-stu-id="3a980-155">The following example shows how to apply attributes to methods, method parameters, and method return values in C#.</span></span>  
  
```csharp  
// default: applies to method  
[SomeAttr]  
int Method1() { return 0; }  
  
// applies to method  
[method: SomeAttr]  
int Method2() { return 0; }  
  
// applies to return value  
[return: SomeAttr]  
int Method3() { return 0; }  
```  
  
> [!NOTE]
>  <span data-ttu-id="3a980-156">无论在哪个目标上将 `SomeAttr` 定义为有效，都必须指定 `return` 目标，即使 `SomeAttr` 定义为仅应用于返回值也是如此。</span><span class="sxs-lookup"><span data-stu-id="3a980-156">Regardless of the targets on which `SomeAttr` is defined to be valid, the `return` target has to be specified, even if `SomeAttr` were defined to apply only to return values.</span></span> <span data-ttu-id="3a980-157">换言之，编译器不会使用 `AttributeUsage` 信息来解析不明确的特性目标。</span><span class="sxs-lookup"><span data-stu-id="3a980-157">In other words, the compiler will not use `AttributeUsage` information to resolve ambiguous attribute targets.</span></span> <span data-ttu-id="3a980-158">有关详细信息，请参阅 [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md)。</span><span class="sxs-lookup"><span data-stu-id="3a980-158">For more information, see [AttributeUsage (C#)](../../../../csharp/programming-guide/concepts/attributes/attributeusage.md).</span></span>  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="3a980-159">特性的常见用途</span><span class="sxs-lookup"><span data-stu-id="3a980-159">Common Uses for Attributes</span></span>  
 <span data-ttu-id="3a980-160">下面列出了代码中特性的一些常见用途：</span><span class="sxs-lookup"><span data-stu-id="3a980-160">The following list includes a few of the common uses of attributes in code:</span></span>  
  
-   <span data-ttu-id="3a980-161">在 Web 服务中使用 `WebMethod` 特性标记方法，以指明方法应可通过 SOAP 协议进行调用。</span><span class="sxs-lookup"><span data-stu-id="3a980-161">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="3a980-162">有关详细信息，请参阅<xref:System.Web.Services.WebMethodAttribute>。</span><span class="sxs-lookup"><span data-stu-id="3a980-162">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
-   <span data-ttu-id="3a980-163">描述在与本机代码互操作时如何封送方法参数。</span><span class="sxs-lookup"><span data-stu-id="3a980-163">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="3a980-164">有关详细信息，请参阅<xref:System.Runtime.InteropServices.MarshalAsAttribute>。</span><span class="sxs-lookup"><span data-stu-id="3a980-164">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
-   <span data-ttu-id="3a980-165">描述类、方法和接口的 COM 属性。</span><span class="sxs-lookup"><span data-stu-id="3a980-165">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
-   <span data-ttu-id="3a980-166">使用 <xref:System.Runtime.InteropServices.DllImportAttribute> 类调用非托管代码。</span><span class="sxs-lookup"><span data-stu-id="3a980-166">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
-   <span data-ttu-id="3a980-167">从标题、版本、说明或商标方面描述程序集。</span><span class="sxs-lookup"><span data-stu-id="3a980-167">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
-   <span data-ttu-id="3a980-168">描述要序列化并暂留类的哪些成员。</span><span class="sxs-lookup"><span data-stu-id="3a980-168">Describing which members of a class to serialize for persistence.</span></span>  
  
-   <span data-ttu-id="3a980-169">描述如何为了执行 XML 序列化在类成员和 XML 节点之间进行映射。</span><span class="sxs-lookup"><span data-stu-id="3a980-169">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
-   <span data-ttu-id="3a980-170">描述的方法的安全要求。</span><span class="sxs-lookup"><span data-stu-id="3a980-170">Describing the security requirements for methods.</span></span>  
  
-   <span data-ttu-id="3a980-171">指定用于强制实施安全规范的特征。</span><span class="sxs-lookup"><span data-stu-id="3a980-171">Specifying characteristics used to enforce security.</span></span>  
  
-   <span data-ttu-id="3a980-172">通过实时 (JIT) 编译器控制优化，这样代码就一直都易于调试。</span><span class="sxs-lookup"><span data-stu-id="3a980-172">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
-   <span data-ttu-id="3a980-173">获取方法调用方的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3a980-173">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="3a980-174">相关章节</span><span class="sxs-lookup"><span data-stu-id="3a980-174">Related Sections</span></span>  
 <span data-ttu-id="3a980-175">有关详细信息，请参见:</span><span class="sxs-lookup"><span data-stu-id="3a980-175">For more information, see:</span></span>  
  
-   [<span data-ttu-id="3a980-176">创建自定义特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a980-176">Creating Custom Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
-   [<span data-ttu-id="3a980-177">使用反射访问特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a980-177">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
-   [<span data-ttu-id="3a980-178">如何：使用特性创建 C/C++ 联合 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a980-178">How to: Create a C/C++ Union by Using Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
-   [<span data-ttu-id="3a980-179">通用特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a980-179">Common Attributes (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/common-attributes.md)  
  
-   [<span data-ttu-id="3a980-180">调用方信息 (C#)</span><span class="sxs-lookup"><span data-stu-id="3a980-180">Caller Information (C#)</span></span>](../../../../csharp/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="3a980-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a980-181">See Also</span></span>  
 <span data-ttu-id="3a980-182">[C# 编程指南](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3a980-182">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="3a980-183">[反射 (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="3a980-183">[Reflection (C#)](../../../../csharp/programming-guide/concepts/reflection.md) </span></span>  
 [<span data-ttu-id="3a980-184">特性</span><span class="sxs-lookup"><span data-stu-id="3a980-184">Attributes</span></span>](https://msdn.microsoft.com/library/5x6cd29c)

