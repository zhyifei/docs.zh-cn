---
title: "公共特性 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 11fe4894-1bf9-4525-a36b-cddcd3a5d22b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9adb5cb378701c8d06a3fa28bad44dc857026b5a
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="common-attributes-visual-basic"></a><span data-ttu-id="9baea-102">公共特性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9baea-102">Common Attributes (Visual Basic)</span></span>
<span data-ttu-id="9baea-103">本主题介绍在 Visual Basic 程序中最常用的属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-103">This topic describes the attributes that are most commonly used in Visual Basic programs.</span></span>  
  
-   [<span data-ttu-id="9baea-104">全局属性</span><span class="sxs-lookup"><span data-stu-id="9baea-104">Global Attributes</span></span>](#Global)  
  
-   [<span data-ttu-id="9baea-105">已过时的特性</span><span class="sxs-lookup"><span data-stu-id="9baea-105">Obsolete Attribute</span></span>](#Obsolete)  
  
-   [<span data-ttu-id="9baea-106">条件属性</span><span class="sxs-lookup"><span data-stu-id="9baea-106">Conditional Attribute</span></span>](#Conditional)  
  
-   [<span data-ttu-id="9baea-107">调用方信息特性</span><span class="sxs-lookup"><span data-stu-id="9baea-107">Caller Info Attributes</span></span>](#CallerInfo)  
  
-   [<span data-ttu-id="9baea-108">Visual Basic 特性</span><span class="sxs-lookup"><span data-stu-id="9baea-108">Visual Basic Attributes</span></span>](#VB)  
  
##  <span data-ttu-id="9baea-109"><a name="Global"></a>全局属性</span><span class="sxs-lookup"><span data-stu-id="9baea-109"><a name="Global"></a> Global Attributes</span></span>  
 <span data-ttu-id="9baea-110">大多数属性应用于特定语言元素，如类或方法; 这些方法但是，有些属性是全局 — 它们应用于整个程序集或模块。</span><span class="sxs-lookup"><span data-stu-id="9baea-110">Most attributes are applied to specific language elements such as classes or methods; however, some attributes are global—they apply to an entire assembly or module.</span></span> <span data-ttu-id="9baea-111">例如，<xref:System.Reflection.AssemblyVersionAttribute>属性可用于嵌入到程序集，像这样的版本信息︰</xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-111">For example, the <xref:System.Reflection.AssemblyVersionAttribute> attribute can be used to embed version information into an assembly, like this:</span></span>  
  
```vb  
<Assembly: AssemblyVersion("1.0.0.0")>  
```  
  
 <span data-ttu-id="9baea-112">全局属性在任何后会出现在源代码中顶级`Imports`语句和任何类型、 模块或命名空间声明之前。</span><span class="sxs-lookup"><span data-stu-id="9baea-112">Global attributes appear in the source code after any top-level`Imports` statements and before any type, module, or namespace declarations.</span></span> <span data-ttu-id="9baea-113">全局特性可以出现在多个源文件，但必须在单一编译传递中编译这些文件。</span><span class="sxs-lookup"><span data-stu-id="9baea-113">Global attributes can appear in multiple source files, but the files must be compiled in a single compilation pass.</span></span> <span data-ttu-id="9baea-114">对于 Visual Basic 项目，通常将全局属性放在 AssemblyInfo.vb 文件 （该文件自动创建在 Visual Studio 中创建项目时）。</span><span class="sxs-lookup"><span data-stu-id="9baea-114">For Visual Basic projects, global attributes are generally put in the AssemblyInfo.vb file (the file is created automatically when you create a project in Visual Studio).</span></span>  
  
 <span data-ttu-id="9baea-115">程序集特性是提供程序集相关信息的值。</span><span class="sxs-lookup"><span data-stu-id="9baea-115">Assembly attributes are values that provide information about an assembly.</span></span> <span data-ttu-id="9baea-116">这些内容分为以下类别︰</span><span class="sxs-lookup"><span data-stu-id="9baea-116">They fall into the following categories:</span></span>  
  
-   <span data-ttu-id="9baea-117">程序集标识属性</span><span class="sxs-lookup"><span data-stu-id="9baea-117">Assembly identity attributes</span></span>  
  
-   <span data-ttu-id="9baea-118">信息性特性</span><span class="sxs-lookup"><span data-stu-id="9baea-118">Informational attributes</span></span>  
  
-   <span data-ttu-id="9baea-119">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="9baea-119">Assembly manifest attributes</span></span>  
  
### <a name="assembly-identity-attributes"></a><span data-ttu-id="9baea-120">程序集标识特性。</span><span class="sxs-lookup"><span data-stu-id="9baea-120">Assembly Identity Attributes</span></span>  
 <span data-ttu-id="9baea-121">三个特性 （还有一个强名称，如果适用） 确定程序集的标识︰ 名称、 版本和区域性。</span><span class="sxs-lookup"><span data-stu-id="9baea-121">Three attributes (with a strong name, if applicable) determine the identity of an assembly: name, version, and culture.</span></span> <span data-ttu-id="9baea-122">这些属性构成该程序集的完整名称和时，需要在代码中引用。</span><span class="sxs-lookup"><span data-stu-id="9baea-122">These attributes form the full name of the assembly and are required when you reference it in code.</span></span> <span data-ttu-id="9baea-123">您可以设置程序集的版本和使用属性的区域性。</span><span class="sxs-lookup"><span data-stu-id="9baea-123">You can set an assembly's version and culture using attributes.</span></span> <span data-ttu-id="9baea-124">但是，由编译器，Visual Studio IDE 中设置的名称值[程序集信息对话框](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box)，或程序集链接器 (Al.exe) 创建程序集，基于包含程序集清单的文件。</span><span class="sxs-lookup"><span data-stu-id="9baea-124">However, the name value is set by the compiler, the Visual Studio IDE in the [Assembly Information Dialog Box](https://docs.microsoft.com/visualstudio/ide/reference/assembly-information-dialog-box), or the Assembly Linker (Al.exe) when the assembly is created, based on the file that contains the assembly manifest.</span></span> <span data-ttu-id="9baea-125"><xref:System.Reflection.AssemblyFlagsAttribute>属性指定的程序集的多个副本可以相互共存。</xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-125">The <xref:System.Reflection.AssemblyFlagsAttribute> attribute specifies whether multiple copies of the assembly can coexist.</span></span>  
  
 <span data-ttu-id="9baea-126">下表显示标识属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-126">The following table shows the identity attributes.</span></span>  
  
|<span data-ttu-id="9baea-127">特性</span><span class="sxs-lookup"><span data-stu-id="9baea-127">Attribute</span></span>|<span data-ttu-id="9baea-128">目标</span><span class="sxs-lookup"><span data-stu-id="9baea-128">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="9baea-129"><xref:System.Reflection.AssemblyName></xref:System.Reflection.AssemblyName></span><span class="sxs-lookup"><span data-stu-id="9baea-129"><xref:System.Reflection.AssemblyName></span></span>|<span data-ttu-id="9baea-130">详细描述程序集的标识。</span><span class="sxs-lookup"><span data-stu-id="9baea-130">Fully describes the identity of an assembly.</span></span>|  
|<span data-ttu-id="9baea-131"><xref:System.Reflection.AssemblyVersionAttribute></xref:System.Reflection.AssemblyVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-131"><xref:System.Reflection.AssemblyVersionAttribute></span></span>|<span data-ttu-id="9baea-132">指定程序集的版本。</span><span class="sxs-lookup"><span data-stu-id="9baea-132">Specifies the version of an assembly.</span></span>|  
|<span data-ttu-id="9baea-133"><xref:System.Reflection.AssemblyCultureAttribute></xref:System.Reflection.AssemblyCultureAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-133"><xref:System.Reflection.AssemblyCultureAttribute></span></span>|<span data-ttu-id="9baea-134">指定程序集支持的区域性。</span><span class="sxs-lookup"><span data-stu-id="9baea-134">Specifies which culture the assembly supports.</span></span>|  
|<span data-ttu-id="9baea-135"><xref:System.Reflection.AssemblyFlagsAttribute></xref:System.Reflection.AssemblyFlagsAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-135"><xref:System.Reflection.AssemblyFlagsAttribute></span></span>|<span data-ttu-id="9baea-136">指定程序集是否支持在相同的过程中，或在同一应用程序域中的同一计算机上的并行执行。</span><span class="sxs-lookup"><span data-stu-id="9baea-136">Specifies whether an assembly supports side-by-side execution on the same computer, in the same process, or in the same application domain.</span></span>|  
  
### <a name="informational-attributes"></a><span data-ttu-id="9baea-137">信息性特性</span><span class="sxs-lookup"><span data-stu-id="9baea-137">Informational Attributes</span></span>  
 <span data-ttu-id="9baea-138">信息性特性可用于提供程序集的其他公司或产品信息。</span><span class="sxs-lookup"><span data-stu-id="9baea-138">You can use informational attributes to provide additional company or product information for an assembly.</span></span> <span data-ttu-id="9baea-139">下表显示中定义的信息性特性<xref:System.Reflection?displayProperty=fullName>命名空间。</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9baea-139">The following table shows the informational attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="9baea-140">特性</span><span class="sxs-lookup"><span data-stu-id="9baea-140">Attribute</span></span>|<span data-ttu-id="9baea-141">目标</span><span class="sxs-lookup"><span data-stu-id="9baea-141">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="9baea-142"><xref:System.Reflection.AssemblyProductAttribute></xref:System.Reflection.AssemblyProductAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-142"><xref:System.Reflection.AssemblyProductAttribute></span></span>|<span data-ttu-id="9baea-143">定义指定程序集清单的产品名称的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-143">Defines a custom attribute that specifies a product name for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-144"><xref:System.Reflection.AssemblyTrademarkAttribute></xref:System.Reflection.AssemblyTrademarkAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-144"><xref:System.Reflection.AssemblyTrademarkAttribute></span></span>|<span data-ttu-id="9baea-145">定义一个自定义特性指定为程序集清单的商标。</span><span class="sxs-lookup"><span data-stu-id="9baea-145">Defines a custom attribute that specifies a trademark for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></xref:System.Reflection.AssemblyInformationalVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-146"><xref:System.Reflection.AssemblyInformationalVersionAttribute></span></span>|<span data-ttu-id="9baea-147">定义指定的程序集清单是信息性版本的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-147">Defines a custom attribute that specifies an informational version for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-148"><xref:System.Reflection.AssemblyCompanyAttribute></xref:System.Reflection.AssemblyCompanyAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-148"><xref:System.Reflection.AssemblyCompanyAttribute></span></span>|<span data-ttu-id="9baea-149">定义指定公司名称为程序集清单的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-149">Defines a custom attribute that specifies a company name for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-150"><xref:System.Reflection.AssemblyCopyrightAttribute></xref:System.Reflection.AssemblyCopyrightAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-150"><xref:System.Reflection.AssemblyCopyrightAttribute></span></span>|<span data-ttu-id="9baea-151">定义一个自定义特性指定为程序集清单版权。</span><span class="sxs-lookup"><span data-stu-id="9baea-151">Defines a custom attribute that specifies a copyright for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-152"><xref:System.Reflection.AssemblyFileVersionAttribute></xref:System.Reflection.AssemblyFileVersionAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-152"><xref:System.Reflection.AssemblyFileVersionAttribute></span></span>|<span data-ttu-id="9baea-153">指示编译器使用 Win32 文件版本资源特定的版本号。</span><span class="sxs-lookup"><span data-stu-id="9baea-153">Instructs the compiler to use a specific version number for the Win32 file version resource.</span></span>|  
|<span data-ttu-id="9baea-154"><xref:System.CLSCompliantAttribute></xref:System.CLSCompliantAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-154"><xref:System.CLSCompliantAttribute></span></span>|<span data-ttu-id="9baea-155">指示该程序集是否符合公共语言规范 (CLS)。</span><span class="sxs-lookup"><span data-stu-id="9baea-155">Indicates whether the assembly is compliant with the Common Language Specification (CLS).</span></span>|  
  
### <a name="assembly-manifest-attributes"></a><span data-ttu-id="9baea-156">程序集清单特性</span><span class="sxs-lookup"><span data-stu-id="9baea-156">Assembly Manifest Attributes</span></span>  
 <span data-ttu-id="9baea-157">程序集清单特性可用于提供程序集清单中的信息。</span><span class="sxs-lookup"><span data-stu-id="9baea-157">You can use assembly manifest attributes to provide information in the assembly manifest.</span></span> <span data-ttu-id="9baea-158">这包括标题、 说明、 默认别名和配置。</span><span class="sxs-lookup"><span data-stu-id="9baea-158">This includes title, description, default alias, and configuration.</span></span> <span data-ttu-id="9baea-159">下表显示中定义的程序集清单特性<xref:System.Reflection?displayProperty=fullName>命名空间。</xref:System.Reflection?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9baea-159">The following table shows the assembly manifest attributes defined in the <xref:System.Reflection?displayProperty=fullName> namespace.</span></span>  
  
|<span data-ttu-id="9baea-160">特性</span><span class="sxs-lookup"><span data-stu-id="9baea-160">Attribute</span></span>|<span data-ttu-id="9baea-161">目标</span><span class="sxs-lookup"><span data-stu-id="9baea-161">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="9baea-162"><xref:System.Reflection.AssemblyTitleAttribute></xref:System.Reflection.AssemblyTitleAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-162"><xref:System.Reflection.AssemblyTitleAttribute></span></span>|<span data-ttu-id="9baea-163">定义指定为程序集清单的程序集标题的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-163">Defines a custom attribute that specifies an assembly title for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-164"><xref:System.Reflection.AssemblyDescriptionAttribute></xref:System.Reflection.AssemblyDescriptionAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-164"><xref:System.Reflection.AssemblyDescriptionAttribute></span></span>|<span data-ttu-id="9baea-165">定义指定程序集清单的程序集描述的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-165">Defines a custom attribute that specifies an assembly description for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-166"><xref:System.Reflection.AssemblyConfigurationAttribute></xref:System.Reflection.AssemblyConfigurationAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-166"><xref:System.Reflection.AssemblyConfigurationAttribute></span></span>|<span data-ttu-id="9baea-167">为程序集清单中定义的指定程序集配置 （如发布或调试） 的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-167">Defines a custom attribute that specifies an assembly configuration (such as retail or debug) for an assembly manifest.</span></span>|  
|<span data-ttu-id="9baea-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></xref:System.Reflection.AssemblyDefaultAliasAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-168"><xref:System.Reflection.AssemblyDefaultAliasAttribute></span></span>|<span data-ttu-id="9baea-169">定义程序集清单的友好默认别名</span><span class="sxs-lookup"><span data-stu-id="9baea-169">Defines a friendly default alias for an assembly manifest</span></span>|  
  
##  <span data-ttu-id="9baea-170"><a name="Obsolete"></a>已过时的特性</span><span class="sxs-lookup"><span data-stu-id="9baea-170"><a name="Obsolete"></a> Obsolete Attribute</span></span>  
 <span data-ttu-id="9baea-171">`Obsolete`特性标记为不再推荐使用的一个程序实体。</span><span class="sxs-lookup"><span data-stu-id="9baea-171">The `Obsolete` attribute marks a program entity as one that is no longer recommended for use.</span></span> <span data-ttu-id="9baea-172">每个使用标记为已过时的实体随后将生成警告或错误，具体取决于该属性的配置方式。</span><span class="sxs-lookup"><span data-stu-id="9baea-172">Each use of an entity marked obsolete will subsequently generate a warning or an error, depending on how the attribute is configured.</span></span> <span data-ttu-id="9baea-173">例如: </span><span class="sxs-lookup"><span data-stu-id="9baea-173">For example:</span></span>  
  
```vb  
<System.Obsolete("use class B")>   
Class A  
    Sub Method()  
    End Sub  
End Class  
  
Class B  
    <System.Obsolete("use NewMethod", True)>   
    Sub OldMethod()  
    End Sub  
  
    Sub NewMethod()  
    End Sub  
End Class  
```  
  
 <span data-ttu-id="9baea-174">在此示例中`Obsolete`属性应用到类`A`和方法`B.OldMethod`。</span><span class="sxs-lookup"><span data-stu-id="9baea-174">In this example the `Obsolete` attribute is applied to class `A` and to method `B.OldMethod`.</span></span> <span data-ttu-id="9baea-175">因为特性构造函数的第二个参数应用于`B.OldMethod`设置为`true`，此方法将导致编译器错误，而使用类`A`只会产生一条警告。</span><span class="sxs-lookup"><span data-stu-id="9baea-175">Because the second argument of the attribute constructor applied to `B.OldMethod` is set to `true`, this method will cause a compiler error, whereas using class `A` will just produce a warning.</span></span> <span data-ttu-id="9baea-176">调用`B.NewMethod`，然而，将生成任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="9baea-176">Calling `B.NewMethod`, however, produces no warning or error.</span></span>  
  
 <span data-ttu-id="9baea-177">作为第一个参数传递给特性构造函数提供的字符串都显示为警告或错误的一部分。</span><span class="sxs-lookup"><span data-stu-id="9baea-177">The string provided as the first argument to attribute constructor will be displayed as part of the warning or error.</span></span> <span data-ttu-id="9baea-178">例如，当您使用它前面的定义，下面的代码将生成两个警告和一个错误︰</span><span class="sxs-lookup"><span data-stu-id="9baea-178">For example, when you use it with the previous definitions, the following code generates two warnings and one error:</span></span>  
  
```vb  
' Generates 2 warnings:  
' Dim a As New A  
' Generate no errors or warnings:  
  
Dim b As New B  
b.NewMethod()  
  
' Generates an error, terminating compilation:  
' b.OldMethod()  
```  
  
 <span data-ttu-id="9baea-179">类有两个警告`A`生成︰ 一个用于类引用声明，另一个用于类构造函数。</span><span class="sxs-lookup"><span data-stu-id="9baea-179">Two warnings for class `A` are generated: one for the declaration of the class reference, and one for the class constructor.</span></span>  
  
 <span data-ttu-id="9baea-180">`Obsolete`属性可以使用不带参数，但其中的原因包括项已过时，并改为使用哪种建议。</span><span class="sxs-lookup"><span data-stu-id="9baea-180">The `Obsolete` attribute can be used without arguments, but including an explanation of why the item is obsolete and what to use instead is recommended.</span></span>  
  
 <span data-ttu-id="9baea-181">`Obsolete`属性是一个单用途属性和可以应用于任何允许属性的实体。</span><span class="sxs-lookup"><span data-stu-id="9baea-181">The `Obsolete` attribute is a single-use attribute and can be applied to any entity that allows attributes.</span></span> <span data-ttu-id="9baea-182">`Obsolete`是<xref:System.ObsoleteAttribute>。</xref:System.ObsoleteAttribute>的别名</span><span class="sxs-lookup"><span data-stu-id="9baea-182">`Obsolete` is an alias for <xref:System.ObsoleteAttribute>.</span></span>  
  
##  <span data-ttu-id="9baea-183"><a name="Conditional"></a>条件属性</span><span class="sxs-lookup"><span data-stu-id="9baea-183"><a name="Conditional"></a> Conditional Attribute</span></span>  
 <span data-ttu-id="9baea-184">`Conditional`属性使执行方法依赖于预处理标识符。</span><span class="sxs-lookup"><span data-stu-id="9baea-184">The `Conditional` attribute makes the execution of a method dependent on a preprocessing identifier.</span></span> <span data-ttu-id="9baea-185">`Conditional`属性是其别名<xref:System.Diagnostics.ConditionalAttribute>，并可以应用于方法或属性类</xref:System.Diagnostics.ConditionalAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-185">The `Conditional` attribute is an alias for <xref:System.Diagnostics.ConditionalAttribute>, and can be applied to a method or an attribute class.</span></span>  
  
 <span data-ttu-id="9baea-186">在此示例中，`Conditional`应用于方法，以启用或禁用特定于程序的诊断信息的显示︰</span><span class="sxs-lookup"><span data-stu-id="9baea-186">In this example, `Conditional` is applied to a method to enable or disable the display of program-specific diagnostic information:</span></span>  
  
```vb  
#Const TRACE_ON = True  
Imports System  
Imports System.Diagnostics  
Module TestConditionalAttribute  
    Public Class Trace  
        <Conditional("TRACE_ON")>   
        Public Shared Sub Msg(ByVal msg As String)  
            Console.WriteLine(msg)  
        End Sub  
  
    End Class  
  
    Sub Main()  
        Trace.Msg("Now in Main...")  
        Console.WriteLine("Done.")  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="9baea-187">如果`TRACE_ON`未定义标识符时，将显示任何跟踪输出。</span><span class="sxs-lookup"><span data-stu-id="9baea-187">If the `TRACE_ON` identifier is not defined, no trace output will be displayed.</span></span>  
  
 <span data-ttu-id="9baea-188">`Conditional`属性通常用于`DEBUG`标识符来启用跟踪和日志记录功能，实现 debug，但不是在发布版本，如下所示︰</span><span class="sxs-lookup"><span data-stu-id="9baea-188">The `Conditional` attribute is often used with the `DEBUG` identifier to enable trace and logging features for debug builds but not in release builds, like this:</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Shared Sub DebugMethod()  
  
End Sub  
```  
  
 <span data-ttu-id="9baea-189">当调用一个方法标记为条件时，是包含还是省略该调用会确定存在指定的预处理符号。</span><span class="sxs-lookup"><span data-stu-id="9baea-189">When a method marked as conditional is called, the presence or absence of the specified preprocessing symbol determines whether the call is included or omitted.</span></span> <span data-ttu-id="9baea-190">如果定义了该符号，则将包括调用;否则，将忽略该调用。</span><span class="sxs-lookup"><span data-stu-id="9baea-190">If the symbol is defined, the call is included; otherwise, the call is omitted.</span></span> <span data-ttu-id="9baea-191">使用`Conditional`是整洁、 为封闭方法中的替代方法更为妥当，并且不容易出错`#if…#endif`块，如下︰</span><span class="sxs-lookup"><span data-stu-id="9baea-191">Using `Conditional` is a cleaner, more elegant, and less error-prone alternative to enclosing methods inside `#if…#endif` blocks, like this:</span></span>  
  
```vb  
#If DEBUG Then  
    Sub ConditionalMethod()  
    End Sub  
#End If  
```  
  
 <span data-ttu-id="9baea-192">条件的方法必须是类或结构声明中的方法，而且必须没有返回值。</span><span class="sxs-lookup"><span data-stu-id="9baea-192">A conditional method must be a method in a class or struct declaration and must not have a return value.</span></span>  
  
### <a name="using-multiple-identifiers"></a><span data-ttu-id="9baea-193">使用多个标识符</span><span class="sxs-lookup"><span data-stu-id="9baea-193">Using Multiple Identifiers</span></span>  
 <span data-ttu-id="9baea-194">如果某个方法具有多个`Conditional`属性，对方法的调用则将包含定义了至少其中一个条件符号 （换而言之，这些符号在逻辑上连接在一起通过使用或运算符）。</span><span class="sxs-lookup"><span data-stu-id="9baea-194">If a method has multiple `Conditional` attributes, a call to the method is included if at least one of the conditional symbols is defined (in other words, the symbols are logically linked together by using the OR operator).</span></span> <span data-ttu-id="9baea-195">在此示例中，或者是否存在`A`或`B`，则会在方法调用︰</span><span class="sxs-lookup"><span data-stu-id="9baea-195">In this example, the presence of either `A` or `B` will result in a method call:</span></span>  
  
```vb  
<Conditional("A"), Conditional("B")>   
Shared Sub DoIfAorB()  
  
End Sub  
```  
  
 <span data-ttu-id="9baea-196">若要实现在逻辑上将符号链接通过与运算符的效果，可以定义序列条件方法。</span><span class="sxs-lookup"><span data-stu-id="9baea-196">To achieve the effect of logically linking symbols by using the AND operator, you can define serial conditional methods.</span></span> <span data-ttu-id="9baea-197">例如，将执行下面的第二个方法，仅当`A`和`B`定义︰</span><span class="sxs-lookup"><span data-stu-id="9baea-197">For example, the second method below will execute only if both `A` and `B` are defined:</span></span>  
  
```vb  
<Conditional("A")>   
Shared Sub DoIfA()  
    DoIfAandB()  
End Sub  
  
<Conditional("B")>   
Shared Sub DoIfAandB()  
    ' Code to execute when both A and B are defined...  
End Sub  
```  
  
### <a name="using-conditional-with-attribute-classes"></a><span data-ttu-id="9baea-198">使用具有特性类的条件</span><span class="sxs-lookup"><span data-stu-id="9baea-198">Using Conditional with Attribute Classes</span></span>  
 <span data-ttu-id="9baea-199">`Conditional`特性还可应用于属性类定义。</span><span class="sxs-lookup"><span data-stu-id="9baea-199">The `Conditional` attribute can also be applied to an attribute class definition.</span></span> <span data-ttu-id="9baea-200">在此示例中，自定义特性`Documentation`将只将信息添加到元数据如果定义了 DEBUG 时。</span><span class="sxs-lookup"><span data-stu-id="9baea-200">In this example, the custom attribute `Documentation` will only add information to the metadata if DEBUG is defined.</span></span>  
  
```vb  
<Conditional("DEBUG")>   
Public Class Documentation  
    Inherits System.Attribute  
    Private text As String  
    Sub New(ByVal doc_text As String)  
        text = doc_text  
    End Sub  
End Class  
  
Class SampleClass  
    ' This attribute will only be included if DEBUG is defined.  
    <Documentation("This method displays an integer.")>   
    Shared Sub DoWork(ByVal i As Integer)  
        System.Console.WriteLine(i)  
    End Sub  
End Class  
```  
  
##  <span data-ttu-id="9baea-201"><a name="CallerInfo"></a>调用方信息特性</span><span class="sxs-lookup"><span data-stu-id="9baea-201"><a name="CallerInfo"></a> Caller Info Attributes</span></span>  
 <span data-ttu-id="9baea-202">通过使用调用方信息特性，可获取有关方法的调用方的信息。</span><span class="sxs-lookup"><span data-stu-id="9baea-202">By using Caller Info attributes, you can obtain information about the caller to a method.</span></span> <span data-ttu-id="9baea-203">您可以获取源代码的文件路径、 源代码和调用方的成员名称中的行号。</span><span class="sxs-lookup"><span data-stu-id="9baea-203">You can obtain the file path of the source code, the line number in the source code, and the member name of the caller.</span></span>  
  
 <span data-ttu-id="9baea-204">若要获取成员调用方信息，您可以使用应用于可选参数的属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-204">To obtain member caller information, you use attributes that are applied to optional parameters.</span></span> <span data-ttu-id="9baea-205">每个可选参数指定默认值。</span><span class="sxs-lookup"><span data-stu-id="9baea-205">Each optional parameter specifies a default value.</span></span> <span data-ttu-id="9baea-206">下表列出了在中定义的调用方信息特性<xref:System.Runtime.CompilerServices?displayProperty=fullName>命名空间︰</xref:System.Runtime.CompilerServices?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="9baea-206">The following table lists the Caller Info attributes that are defined in the <xref:System.Runtime.CompilerServices?displayProperty=fullName> namespace:</span></span>  
  
|<span data-ttu-id="9baea-207">特性</span><span class="sxs-lookup"><span data-stu-id="9baea-207">Attribute</span></span>|<span data-ttu-id="9baea-208">描述</span><span class="sxs-lookup"><span data-stu-id="9baea-208">Description</span></span>|<span data-ttu-id="9baea-209">类型</span><span class="sxs-lookup"><span data-stu-id="9baea-209">Type</span></span>|  
|---|---|---|  
|<span data-ttu-id="9baea-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-210"><xref:System.Runtime.CompilerServices.CallerFilePathAttribute></span></span>|<span data-ttu-id="9baea-211">包含调用方的源文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="9baea-211">Full path of the source file that contains the caller.</span></span> <span data-ttu-id="9baea-212">这是在编译时的路径。</span><span class="sxs-lookup"><span data-stu-id="9baea-212">This is the path at compile time.</span></span>|`String`|  
|<span data-ttu-id="9baea-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-213"><xref:System.Runtime.CompilerServices.CallerLineNumberAttribute></span></span>|<span data-ttu-id="9baea-214">从中调用该方法的源文件中的行号。</span><span class="sxs-lookup"><span data-stu-id="9baea-214">Line number in the source file from which the method is called.</span></span>|`Integer`|  
|<span data-ttu-id="9baea-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-215"><xref:System.Runtime.CompilerServices.CallerMemberNameAttribute></span></span>|<span data-ttu-id="9baea-216">方法名称或调用方的属性名称。</span><span class="sxs-lookup"><span data-stu-id="9baea-216">Method name or property name of the caller.</span></span> <span data-ttu-id="9baea-217">有关详细信息，请参阅[调用方信息 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/caller-information.md)。</span><span class="sxs-lookup"><span data-stu-id="9baea-217">For more information, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>|`String`|  
  
 <span data-ttu-id="9baea-218">有关调用方信息特性的详细信息，请参阅[调用方信息 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/caller-information.md)。</span><span class="sxs-lookup"><span data-stu-id="9baea-218">For more information about the Caller Info attributes, see [Caller Information (Visual Basic)](../../../../visual-basic/programming-guide/concepts/caller-information.md).</span></span>  
  
##  <span data-ttu-id="9baea-219"><a name="VB"></a>Visual Basic 特性</span><span class="sxs-lookup"><span data-stu-id="9baea-219"><a name="VB"></a> Visual Basic Attributes</span></span>  
 <span data-ttu-id="9baea-220">下表列出了 Visual Basic 特有的属性。</span><span class="sxs-lookup"><span data-stu-id="9baea-220">The following table lists the attributes that are specific to Visual Basic.</span></span>  
  
|<span data-ttu-id="9baea-221">特性</span><span class="sxs-lookup"><span data-stu-id="9baea-221">Attribute</span></span>|<span data-ttu-id="9baea-222">目标</span><span class="sxs-lookup"><span data-stu-id="9baea-222">Purpose</span></span>|  
|---------------|-------------|  
|<span data-ttu-id="9baea-223"><xref:Microsoft.VisualBasic.ComClassAttribute></xref:Microsoft.VisualBasic.ComClassAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-223"><xref:Microsoft.VisualBasic.ComClassAttribute></span></span>|<span data-ttu-id="9baea-224">向编译器指示应将此类公开为 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="9baea-224">Indicates to the compiler that the class should be exposed as a COM object.</span></span>|  
|<span data-ttu-id="9baea-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></xref:Microsoft.VisualBasic.HideModuleNameAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-225"><xref:Microsoft.VisualBasic.HideModuleNameAttribute></span></span>|<span data-ttu-id="9baea-226">允许使用所需的模块限定访问模块成员。</span><span class="sxs-lookup"><span data-stu-id="9baea-226">Allows module members to be accessed using only the qualification needed for the module.</span></span>|  
|<span data-ttu-id="9baea-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></xref:Microsoft.VisualBasic.VBFixedStringAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-227"><xref:Microsoft.VisualBasic.VBFixedStringAttribute></span></span>|<span data-ttu-id="9baea-228">与文件输入和输出指定一个固定长度的字符串的大小用于结构中的函数。</span><span class="sxs-lookup"><span data-stu-id="9baea-228">Specifies the size of a fixed-length string in a structure for use with file input and output functions.</span></span>|  
|<span data-ttu-id="9baea-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span><span class="sxs-lookup"><span data-stu-id="9baea-229"><xref:Microsoft.VisualBasic.VBFixedArrayAttribute></span></span>|<span data-ttu-id="9baea-230">使用输入和输出文件指定用于结构中的固定数组的大小的函数。</span><span class="sxs-lookup"><span data-stu-id="9baea-230">Specifies the size of a fixed array in a structure for use with file input and output functions.</span></span>|  
  
### <a name="comclassattribute"></a><span data-ttu-id="9baea-231">COMClassAttribute</span><span class="sxs-lookup"><span data-stu-id="9baea-231">COMClassAttribute</span></span>  
 <span data-ttu-id="9baea-232">使用`COMClassAttribute`来简化从 Visual Basic 创建 COM 组件的过程。</span><span class="sxs-lookup"><span data-stu-id="9baea-232">Use `COMClassAttribute` to simplify the process of creating COM components from Visual Basic.</span></span> <span data-ttu-id="9baea-233">COM 对象是从.NET Framework 程序集，而有很大差异`COMClassAttribute`，你需要遵循的步骤，在 Visual Basic 中生成一个 COM 对象数。</span><span class="sxs-lookup"><span data-stu-id="9baea-233">COM objects are considerably different from .NET Framework assemblies, and without `COMClassAttribute`, you need to follow a number of steps to generate a COM object from Visual Basic.</span></span> <span data-ttu-id="9baea-234">为类标记为`COMClassAttribute`，编译器会自动执行其中很多步骤。</span><span class="sxs-lookup"><span data-stu-id="9baea-234">For classes marked with `COMClassAttribute`, the compiler performs many of these steps automatically.</span></span>  
  
### <a name="hidemodulenameattribute"></a><span data-ttu-id="9baea-235">HideModuleNameAttribute</span><span class="sxs-lookup"><span data-stu-id="9baea-235">HideModuleNameAttribute</span></span>  
 <span data-ttu-id="9baea-236">使用`HideModuleNameAttribute`以允许访问通过使用所需的模块限定模块成员。</span><span class="sxs-lookup"><span data-stu-id="9baea-236">Use `HideModuleNameAttribute` to allow module members to be accessed by using only the qualification needed for the module.</span></span>  
  
### <a name="vbfixedstringattribute"></a><span data-ttu-id="9baea-237">VBFixedStringAttribute</span><span class="sxs-lookup"><span data-stu-id="9baea-237">VBFixedStringAttribute</span></span>  
 <span data-ttu-id="9baea-238">使用`VBFixedStringAttribute`强制 Visual Basic 中创建一个固定长度的字符串。</span><span class="sxs-lookup"><span data-stu-id="9baea-238">Use `VBFixedStringAttribute` to force Visual Basic to create a fixed-length string.</span></span> <span data-ttu-id="9baea-239">字符串的变量长度在默认情况下，并且此特性将字符串存储到文件时很有用。</span><span class="sxs-lookup"><span data-stu-id="9baea-239">Strings are of variable length by default, and this attribute is useful when storing strings to files.</span></span> <span data-ttu-id="9baea-240">下面的代码演示这一︰</span><span class="sxs-lookup"><span data-stu-id="9baea-240">The following code demonstrates this:</span></span>  
  
```vb  
Structure Worker  
    ' The runtime uses VBFixedString to determine   
    ' if the field should be written out as a fixed size.  
    <VBFixedString(10)> Public LastName As String  
    <VBFixedString(7)> Public Title As String  
    <VBFixedString(2)> Public Rank As String  
End Structure  
```  
  
### <a name="vbfixedarrayattribute"></a><span data-ttu-id="9baea-241">VBFixedArrayAttribute</span><span class="sxs-lookup"><span data-stu-id="9baea-241">VBFixedArrayAttribute</span></span>  
 <span data-ttu-id="9baea-242">使用`VBFixedArrayAttribute`声明固定大小的数组。</span><span class="sxs-lookup"><span data-stu-id="9baea-242">Use `VBFixedArrayAttribute` to declare arrays that are fixed in size.</span></span> <span data-ttu-id="9baea-243">Visual Basic 像字符串一样，数组是默认情况下的可变长度。</span><span class="sxs-lookup"><span data-stu-id="9baea-243">Like Visual Basic strings, arrays are of variable length by default.</span></span> <span data-ttu-id="9baea-244">此属性是在序列化或数据写入文件时很有用。</span><span class="sxs-lookup"><span data-stu-id="9baea-244">This attribute is useful when serializing or writing data to files.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9baea-245">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9baea-245">See Also</span></span>  
 <span data-ttu-id="9baea-246"><xref:System.Reflection></xref:System.Reflection></span><span class="sxs-lookup"><span data-stu-id="9baea-246"><xref:System.Reflection></span></span>   
 <span data-ttu-id="9baea-247"><xref:System.Attribute></xref:System.Attribute></span><span class="sxs-lookup"><span data-stu-id="9baea-247"><xref:System.Attribute></span></span>   
<span data-ttu-id="9baea-248"> [Visual Basic 编程指南](../../../../visual-basic/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9baea-248"> [Visual Basic Programming Guide](../../../../visual-basic/programming-guide/index.md) </span></span>  
<span data-ttu-id="9baea-249"> [属性](https://msdn.microsoft.com/library/5x6cd29c) </span><span class="sxs-lookup"><span data-stu-id="9baea-249"> [Attributes](https://msdn.microsoft.com/library/5x6cd29c) </span></span>  
<span data-ttu-id="9baea-250"> [反射 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span><span class="sxs-lookup"><span data-stu-id="9baea-250"> [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md) </span></span>  
<span data-ttu-id="9baea-251"> [使用反射 (Visual Basic 中) 访问特性](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span><span class="sxs-lookup"><span data-stu-id="9baea-251"> [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)</span></span>
