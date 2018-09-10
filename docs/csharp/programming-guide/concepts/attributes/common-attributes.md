---
title: 通用属性 (C#)
ms.date: 07/20/2015
ms.assetid: 785a0526-6c0e-4599-8c61-ccdc88dd9965
ms.openlocfilehash: 3b02b750ad4801177cb2ee4e2ef4bf51ecb2f20f
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43504390"
---
# <a name="common-attributes-c"></a><span data-ttu-id="a0693-102">通用属性 (C#)</span><span class="sxs-lookup"><span data-stu-id="a0693-102">Common Attributes (C#)</span></span>
<span data-ttu-id="a0693-103">本主题介绍在 C# 程序中最常用的属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-103">This topic describes the attributes that are most commonly used in C# programs.</span></span>  
  
-   [<span data-ttu-id="a0693-104">全局特性</span><span class="sxs-lookup"><span data-stu-id="a0693-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="a0693-105">Obsolete 特性</span><span class="sxs-lookup"><span data-stu-id="a0693-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="a0693-106">Conditional 特性</span><span class="sxs-lookup"><span data-stu-id="a0693-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="a0693-107">调用方信息特性</span><span class="sxs-lookup"><span data-stu-id="a0693-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
##  <a name="Global"></a> <span data-ttu-id="a0693-108">全局特性</span><span class="sxs-lookup"><span data-stu-id="a0693-108">Global Attributes</span></span>  
 <span data-ttu-id="a0693-109">大多数特性应用于特定语言元素，如类或方法；但是，一些特性是全局特性 - 它们应用于整个程序集或模块。</span><span class="sxs-lookup"><span data-stu-id="a0693-109">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="a0693-110">例如，<xref:System.Reflection.AssemblyVersionAttribute> 属性可用于将版本信息嵌入程序集，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a0693-110">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```csharp  
[assembly: AssemblyVersion("1.0.0.0")]  
```  
  
 <span data-ttu-id="a0693-111">全局特性出现在源代码中任何顶级 `using` 指令之后和任何类型、模块或命名空间声明之前。</span><span class="sxs-lookup"><span data-stu-id="a0693-111">Global attributes appear in the source code after any top-level `using` directives and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="a0693-112">全局特性可以出现在多个源文件中，但必须在单个编译过程中编译这些文件。</span><span class="sxs-lookup"><span data-stu-id="a0693-112">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="a0693-113">在 C# 项目中，全局特性放在 AssemblyInfo.cs 文件中。</span><span class="sxs-lookup"><span data-stu-id="a0693-113">In C# projects, global attributes are put in the AssemblyInfo.cs file.</span></span>  
  
 <span data-ttu-id="a0693-114">程序集特性是提供程序集相关信息的值。</span><span class="sxs-lookup"><span data-stu-id="a0693-114">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="a0693-115">它们分为以下几类：</span><span class="sxs-lookup"><span data-stu-id="a0693-115">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="a0693-116">程序集标识特性</span><span class="sxs-lookup"><span data-stu-id="a0693-116">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="a0693-117">信息性特性</span><span class="sxs-lookup"><span data-stu-id="a0693-117">Informational attributes</span></span>  
  
-   <span data-ttu-id="a0693-118">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="a0693-118">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="a0693-119">程序集标识特性。</span><span class="sxs-lookup"><span data-stu-id="a0693-119">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="a0693-120">三个特性（与强名称（如果适用））组合起来可以确定程序集的标识：名称、版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="a0693-120">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="a0693-121">这些特性构成程序集的全名，在代码中引用程序集时必需使用。</span><span class="sxs-lookup"><span data-stu-id="a0693-121">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="a0693-122">可使用特性设置程序集的版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="a0693-122">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="a0693-123">但是，创建程序集时，根据包含程序集清单的文件，由编译器、[程序集信息对话框](/visualstudio/ide/reference/assembly-information-dialog-box)中的 Visual Studio IDE 或程序集链接器 (Al.exe) 设置名称值。</span><span class="sxs-lookup"><span data-stu-id="a0693-123">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="a0693-124"><xref:System.Reflection.AssemblyFlagsAttribute> 属性指定程序集的多个副本是否可以共存。</span><span class="sxs-lookup"><span data-stu-id="a0693-124">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="a0693-125">下表显示标识特性。</span><span class="sxs-lookup"><span data-stu-id="a0693-125">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="a0693-126">特性</span><span class="sxs-lookup"><span data-stu-id="a0693-126">Attribute</span></span>|<span data-ttu-id="a0693-127">目标</span><span class="sxs-lookup"><span data-stu-id="a0693-127">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyName>|<span data-ttu-id="a0693-128">详细描述程序集的标识。</span><span class="sxs-lookup"><span data-stu-id="a0693-128">Fully describes the identity of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyVersionAttribute>|<span data-ttu-id="a0693-129">指定程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="a0693-129">Specifies the version of an assembly.</span></span>|  
|<xref:System.Reflection.AssemblyCultureAttribute>|<span data-ttu-id="a0693-130">指定程序集支持的区域性。</span><span class="sxs-lookup"><span data-stu-id="a0693-130">Specifies which culture the assembly supports.</span></span>|  
|<xref:System.Reflection.AssemblyFlagsAttribute>|<span data-ttu-id="a0693-131">指定程序集是否支持在同一计算机上、同一进程中或同一应用程序域中并行执行。</span><span class="sxs-lookup"><span data-stu-id="a0693-131">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="a0693-132">信息性特性</span><span class="sxs-lookup"><span data-stu-id="a0693-132">Informational Attributes</span></span>  
 <span data-ttu-id="a0693-133">信息性特性可用于提供程序集的其他公司或产品信息。</span><span class="sxs-lookup"><span data-stu-id="a0693-133">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="a0693-134">下表显示 <xref:System.Reflection?displayProperty=nameWithType> 命名空间中定义的信息性属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-134">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="a0693-135">特性</span><span class="sxs-lookup"><span data-stu-id="a0693-135">Attribute</span></span>|<span data-ttu-id="a0693-136">目标</span><span class="sxs-lookup"><span data-stu-id="a0693-136">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyProductAttribute>|<span data-ttu-id="a0693-137">定义为程序集清单指定产品名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-137">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyTrademarkAttribute>|<span data-ttu-id="a0693-138">定义为程序集清单指定商标的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-138">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|<span data-ttu-id="a0693-139">定义为程序集清单指定信息性版本的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-139">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCompanyAttribute>|<span data-ttu-id="a0693-140">定义为程序集清单指定公司名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-140">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyCopyrightAttribute>|<span data-ttu-id="a0693-141">定义为程序集清单指定版权的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-141">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyFileVersionAttribute>|<span data-ttu-id="a0693-142">指示编译器使用 Win32 文件版本资源的特定版本号。</span><span class="sxs-lookup"><span data-stu-id="a0693-142">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<xref:System.CLSCompliantAttribute>|<span data-ttu-id="a0693-143">指示程序集是否符合公共语言规范 (CLS)。</span><span class="sxs-lookup"><span data-stu-id="a0693-143">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="a0693-144">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="a0693-144">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="a0693-145">程序集清单特性可用于提供程序集清单中的信息。</span><span class="sxs-lookup"><span data-stu-id="a0693-145">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="a0693-146">这些信息包括标题、说明、默认别名和配置。</span><span class="sxs-lookup"><span data-stu-id="a0693-146">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="a0693-147">下表显示 <xref:System.Reflection?displayProperty=nameWithType> 命名空间中定义的程序集清单属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-147">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=nameWithType> namespace.</span></span>  
  
|<span data-ttu-id="a0693-148">特性</span><span class="sxs-lookup"><span data-stu-id="a0693-148">Attribute</span></span>|<span data-ttu-id="a0693-149">目标</span><span class="sxs-lookup"><span data-stu-id="a0693-149">Purpose</span></span>|  
|---------------|-------------|  
|<xref:System.Reflection.AssemblyTitleAttribute>|<span data-ttu-id="a0693-150">定义为程序集清单指定程序集标题的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-150">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDescriptionAttribute>|<span data-ttu-id="a0693-151">定义为程序集清单指定程序集说明的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-151">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyConfigurationAttribute>|<span data-ttu-id="a0693-152">定义为程序集清单指定程序集配置（如零售或调试）的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="a0693-152">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|<span data-ttu-id="a0693-153">定义程序集清单的友好默认别名</span><span class="sxs-lookup"><span data-stu-id="a0693-153">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <a name="Obsolete"></a> <span data-ttu-id="a0693-154">Obsolete 特性</span><span class="sxs-lookup"><span data-stu-id="a0693-154">Obsolete Attribute</span></span>  
 <span data-ttu-id="a0693-155">`Obsolete` 特性将程序实体标记为不再推荐使用。</span><span class="sxs-lookup"><span data-stu-id="a0693-155">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="a0693-156">每次使用标记为过时的实体后，将生成警告或错误，具体取决于该特性的配置方式。</span><span class="sxs-lookup"><span data-stu-id="a0693-156">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="a0693-157">例如:</span><span class="sxs-lookup"><span data-stu-id="a0693-157">For example:</span></span>  
  
```csharp  
[System.Obsolete("use class B")]  
class A  
{  
    public void Method() { }  
}  
class B  
{  
    [System.Obsolete("use NewMethod", true)]  
    public void OldMethod() { }  
    public void NewMethod() { }  
}  
```  
  
 <span data-ttu-id="a0693-158">在此示例中，`Obsolete` 特性应用于类 `A` 和方法 `B.OldMethod`。</span><span class="sxs-lookup"><span data-stu-id="a0693-158">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="a0693-159">因为应用于 `B.OldMethod` 的特性构造函数的第二个参数设置为 `true`，所以此方法将导致编译器错误，而使用类 `A` 只会生成警告。</span><span class="sxs-lookup"><span data-stu-id="a0693-159">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="a0693-160">但是，调用 `B.NewMethod` 不会生成任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="a0693-160">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="a0693-161">作为特性构造函数的第一个参数提供的字符串将作为警告或错误的一部分显示。</span><span class="sxs-lookup"><span data-stu-id="a0693-161">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="a0693-162">例如，将其与先前的定义一起使用时，以下代码会生成两个警告和一个错误：</span><span class="sxs-lookup"><span data-stu-id="a0693-162">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```csharp  
// Generates 2 warnings:  
// A a = new A();  
  
// Generate no errors or warnings:  
B b = new B();  
b.NewMethod();  
  
// Generates an error, terminating compilation:  
// b.OldMethod();  
```  
  
 <span data-ttu-id="a0693-163">将生成类 `A` 的两个警告：一个用于声明类引用，另一个用于类构造函数。</span><span class="sxs-lookup"><span data-stu-id="a0693-163">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="a0693-164">`Obsolete` 特性可以在不带参数的情况下使用，但建议包括说明项目过时的原因以及改为使用哪个项目。</span><span class="sxs-lookup"><span data-stu-id="a0693-164">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="a0693-165">`Obsolete` 特性是一次性特性，可以应用于任何允许特性的实体。</span><span class="sxs-lookup"><span data-stu-id="a0693-165">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="a0693-166">`Obsolete` 是 <xref:System.ObsoleteAttribute> 的别名。</span><span class="sxs-lookup"><span data-stu-id="a0693-166">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <a name="Conditional"></a> <span data-ttu-id="a0693-167">Conditional 特性</span><span class="sxs-lookup"><span data-stu-id="a0693-167">Conditional Attribute</span></span>  
 <span data-ttu-id="a0693-168">`Conditional` 特性使得方法执行依赖于预处理标识符。</span><span class="sxs-lookup"><span data-stu-id="a0693-168">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="a0693-169">`Conditional` 属性是 <xref:System.Diagnostics.ConditionalAttribute> 的别名，可以应用于方法或特性类。</span><span class="sxs-lookup"><span data-stu-id="a0693-169">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="a0693-170">在此示例中，`Conditional` 应用于启用或禁用显示特定于程序的诊断信息的方法：</span><span class="sxs-lookup"><span data-stu-id="a0693-170">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```csharp  
#define TRACE_ON  
using System;  
using System.Diagnostics;  
  
public class Trace  
{  
    [Conditional("TRACE_ON")]  
    public static void Msg(string msg)  
    {  
        Console.WriteLine(msg);  
    }  
}  
  
public class ProgramClass  
{  
    static void Main()  
    {  
        Trace.Msg("Now in Main...");  
        Console.WriteLine("Done.");  
    }  
}  
```  
  
 <span data-ttu-id="a0693-171">如果未定义 `TRACE_ON` 标识符，则不会显示任何跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="a0693-171">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="a0693-172">`Conditional` 特性通常与 `DEBUG` 标识符一起使用，以启用调试生成（而非发布生成）中的跟踪和日志记录功能，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a0693-172">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
static void DebugMethod()  
{  
}  
```  
  
 <span data-ttu-id="a0693-173">当调用标记为 conditional 的方法时，指定的预处理符号是否存在将决定包括还是省略该调用。</span><span class="sxs-lookup"><span data-stu-id="a0693-173">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="a0693-174">如果定义了符号，则将包括调用；否则，将忽略该调用。</span><span class="sxs-lookup"><span data-stu-id="a0693-174">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="a0693-175">使用 `Conditional` 是将方法封闭在 `#if…#endif` 块内的更简洁且较不容易出错的替代方法，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a0693-175">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```csharp  
#if DEBUG  
    void ConditionalMethod()  
    {  
    }  
#endif  
```  
  
 <span data-ttu-id="a0693-176">条件方法必须是类或结构声明中的方法，而且必须没有返回值。</span><span class="sxs-lookup"><span data-stu-id="a0693-176">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="a0693-177">使用多个标识符</span><span class="sxs-lookup"><span data-stu-id="a0693-177">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="a0693-178">如果某个方法具有多个 `Conditional` 特性，则如果至少定义了其中一个条件符号（换言之，通过使用 OR 运算符将这些符号逻辑链接在一起），则包含对该方法的调用。</span><span class="sxs-lookup"><span data-stu-id="a0693-178">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="a0693-179">在此示例中，存在 `A` 或 `B` 将导致方法调用：</span><span class="sxs-lookup"><span data-stu-id="a0693-179">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```csharp  
[Conditional("A"), Conditional("B")]  
static void DoIfAorB()  
{  
    // ...  
}  
```  
  
 <span data-ttu-id="a0693-180">若要使用 AND 运算符实现逻辑链接符号的效果，可以定义串行条件方法。</span><span class="sxs-lookup"><span data-stu-id="a0693-180">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="a0693-181">例如，仅当同时定义了 `A` 和 `B` 时才会执行下面的第二个方法：</span><span class="sxs-lookup"><span data-stu-id="a0693-181">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```csharp
[Conditional("A")]  
static void DoIfA()  
{  
    DoIfAandB();  
}  
  
[Conditional("B")]  
static void DoIfAandB()  
{  
    // Code to execute when both A and B are defined...  
}  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="a0693-182">将 Conditional 用于特性类</span><span class="sxs-lookup"><span data-stu-id="a0693-182">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="a0693-183">`Conditional` 特性还可应用于特性类定义。</span><span class="sxs-lookup"><span data-stu-id="a0693-183">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="a0693-184">在本示例中，如果定义了 DEBUG，则自定义属性 `Documentation` 将仅向元数据添加信息。</span><span class="sxs-lookup"><span data-stu-id="a0693-184">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```csharp  
[Conditional("DEBUG")]  
public class Documentation : System.Attribute  
{  
    string text;  
  
    public Documentation(string text)  
    {  
        this.text = text;  
    }  
}  
  
class SampleClass  
{  
    // This attribute will only be included if DEBUG is defined.  
    [Documentation("This method displays an integer.")]  
    static void DoWork(int i)  
    {  
        System.Console.WriteLine(i.ToString());  
    }  
}  
```  
  
##  <a name="CallerInfo"></a><span data-ttu-id="a0693-185">调用方信息特性</span><span class="sxs-lookup"><span data-stu-id="a0693-185">Caller Info Attributes</span></span>  
 <span data-ttu-id="a0693-186">通过使用调用方信息特性，可获取有关方法的调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="a0693-186">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="a0693-187">可以获取源代码的文件路径、源代码中的行号和调用方的成员名称。</span><span class="sxs-lookup"><span data-stu-id="a0693-187">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="a0693-188">若要获取成员调用方信息，可以使用应用于可选参数的特性。</span><span class="sxs-lookup"><span data-stu-id="a0693-188">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="a0693-189">每个可选参数指定一个默认值。</span><span class="sxs-lookup"><span data-stu-id="a0693-189">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="a0693-190">下表列出在 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 命名空间中定义的调用方信息特性：</span><span class="sxs-lookup"><span data-stu-id="a0693-190">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> namespace:</span></span>  
  
|<span data-ttu-id="a0693-191">特性</span><span class="sxs-lookup"><span data-stu-id="a0693-191">Attribute</span></span>|<span data-ttu-id="a0693-192">描述</span><span class="sxs-lookup"><span data-stu-id="a0693-192">Description</span></span>|<span data-ttu-id="a0693-193">类型</span><span class="sxs-lookup"><span data-stu-id="a0693-193">Type</span></span>|  
|---|---|---|  
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|<span data-ttu-id="a0693-194">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="a0693-194">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="a0693-195">这是编译时的路径。</span><span class="sxs-lookup"><span data-stu-id="a0693-195">This is the path at compile time.</span></span>|`String`|  
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|<span data-ttu-id="a0693-196">源文件中调用方法的行号。</span><span class="sxs-lookup"><span data-stu-id="a0693-196">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|<span data-ttu-id="a0693-197">调用方的方法名称或属性名称。</span><span class="sxs-lookup"><span data-stu-id="a0693-197">Method name or property name of the caller.</span></span> <span data-ttu-id="a0693-198">有关详细信息，请参阅[调用方信息 (C#)](../../../../csharp/programming-guide/concepts/caller-information.md)。</span><span class="sxs-lookup"><span data-stu-id="a0693-198">For more information, see [Caller Information (C#)](../../../../csharp/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="a0693-199">有关调用方信息特性的详细信息，请参阅[调用方信息 (C#)](../../../../csharp/programming-guide/concepts/caller-information.md)。</span><span class="sxs-lookup"><span data-stu-id="a0693-199">For more information about the Caller Info attributes, see [Caller Information (C#)](../../../../csharp/programming-guide/concepts/caller-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0693-200">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0693-200">See Also</span></span>

- <xref:System.Reflection>  
- <xref:System.Attribute>  
- [<span data-ttu-id="a0693-201">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a0693-201">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="a0693-202">特性</span><span class="sxs-lookup"><span data-stu-id="a0693-202">Attributes</span></span>](../../../../../docs/standard/attributes/index.md)  
- [<span data-ttu-id="a0693-203">反射 (C#)</span><span class="sxs-lookup"><span data-stu-id="a0693-203">Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/reflection.md)  
- [<span data-ttu-id="a0693-204">使用反射访问特性 (C#)</span><span class="sxs-lookup"><span data-stu-id="a0693-204">Accessing Attributes by Using Reflection (C#)</span></span>](../../../../csharp/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)
