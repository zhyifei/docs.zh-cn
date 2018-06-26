---
title: -langversion（C# 编译器选项）
ms.date: 05/14/2018
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 2a9501c883fec7478932b22ea2cdcad70865e0fd
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696281"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="fb9a9-102">-langversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="fb9a9-102">-langversion (C# Compiler Options)</span></span>
<span data-ttu-id="fb9a9-103">使编译器仅接受包含在所选 C# 语言规范中的语法。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb9a9-104">语法</span><span class="sxs-lookup"><span data-stu-id="fb9a9-104">Syntax</span></span>  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="fb9a9-105">自变量</span><span class="sxs-lookup"><span data-stu-id="fb9a9-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="fb9a9-106">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="fb9a9-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="fb9a9-107">选项</span><span class="sxs-lookup"><span data-stu-id="fb9a9-107">Option</span></span>|<span data-ttu-id="fb9a9-108">含义</span><span class="sxs-lookup"><span data-stu-id="fb9a9-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="fb9a9-109">default</span><span class="sxs-lookup"><span data-stu-id="fb9a9-109">default</span></span>|<span data-ttu-id="fb9a9-110">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-110">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="fb9a9-111">ISO-1</span><span class="sxs-lookup"><span data-stu-id="fb9a9-111">ISO-1</span></span>|<span data-ttu-id="fb9a9-112">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法 <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-112">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="fb9a9-113">ISO-2</span><span class="sxs-lookup"><span data-stu-id="fb9a9-113">ISO-2</span></span>|<span data-ttu-id="fb9a9-114">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法 <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-114">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="fb9a9-115">3</span><span class="sxs-lookup"><span data-stu-id="fb9a9-115">3</span></span>|<span data-ttu-id="fb9a9-116">编译器只接受 C# 3.0 或更低版本中所含的语法 <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-116">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="fb9a9-117">4</span><span class="sxs-lookup"><span data-stu-id="fb9a9-117">4</span></span>|<span data-ttu-id="fb9a9-118">编译器只接受 C# 4.0 或更低版本中所含的语法 <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-118">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="fb9a9-119">5</span><span class="sxs-lookup"><span data-stu-id="fb9a9-119">5</span></span>|<span data-ttu-id="fb9a9-120">编译器只接受 C# 5.0 或更低版本中所含的语法 <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-120">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="fb9a9-121">6</span><span class="sxs-lookup"><span data-stu-id="fb9a9-121">6</span></span>|<span data-ttu-id="fb9a9-122">编译器只接受 C# 6.0 或更低版本中所含的语法 <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-122">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="fb9a9-123">7</span><span class="sxs-lookup"><span data-stu-id="fb9a9-123">7</span></span>|<span data-ttu-id="fb9a9-124">编译器只接受 C# 7.0 或更低版本中所含的语法 <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-124">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="fb9a9-125">7.1</span><span class="sxs-lookup"><span data-stu-id="fb9a9-125">7.1</span></span>|<span data-ttu-id="fb9a9-126">编译器只接受 C# 7.1 或更低版本中所含的语法 <sup id="TCS71">[CS71](#FCS71)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-126">The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup></span></span>|
|<span data-ttu-id="fb9a9-127">7.2</span><span class="sxs-lookup"><span data-stu-id="fb9a9-127">7.2</span></span>|<span data-ttu-id="fb9a9-128">编译器只接受 C# 7.2 或更低版本中所含的语法 <sup id="TCS72">[CS72](#FCS72)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-128">The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS72">[CS72](#FCS72)</sup></span></span>|
|<span data-ttu-id="fb9a9-129">7.3</span><span class="sxs-lookup"><span data-stu-id="fb9a9-129">7.3</span></span>|<span data-ttu-id="fb9a9-130">编译器只接受 C# 7.3 或更低版本中所含的语法 <sup id="TCS73">[CS73](#FCS73)</sup></span><span class="sxs-lookup"><span data-stu-id="fb9a9-130">The compiler accepts only syntax that is included in C# 7.3 or lower <sup id="TCS73">[CS73](#FCS73)</sup></span></span>|
|<span data-ttu-id="fb9a9-131">最新</span><span class="sxs-lookup"><span data-stu-id="fb9a9-131">latest</span></span>|<span data-ttu-id="fb9a9-132">编译器接受它可支持的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-132">The compiler accepts all valid language syntax that it can support.</span></span>|

<!--- Uncomment and move these above
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS8">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="fb9a9-133">备注</span><span class="sxs-lookup"><span data-stu-id="fb9a9-133">Remarks</span></span>  
 <span data-ttu-id="fb9a9-134">C# 应用程序引用的元数据不受 -langversion 编译器选项约束。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-134">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="fb9a9-135">每个版本的 C# 编译器都包含语言规范的扩展，因此 -langversion 不提供早期版本编译器的同等功能。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-135">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="fb9a9-136">此外，虽然 C# 版本更新通常与主要的 .NET Framework 版本一致，但新的语法和功能不一定绑定到该特定的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-136">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="fb9a9-137">虽然新功能肯定需要与 C# 修订版一起发布的新编译器更新，但每项具体功能都有自己的最小 .NET API 或公共语言运行时要求，这些要求通过包括 NuGet 包或其他库允许功能在下层框架上运行。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-137">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="fb9a9-138">无论使用哪一项 -langversion 设置，都将使用当前版本的公共语言运行时来创建 .exe 或 .dll。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-138">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="fb9a9-139">友元程序集和 [-moduleassemblyname（C# 编译器选项）](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)是一个例外，它们在 -langversion:ISO-1 下工作。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-139">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  
 
 <span data-ttu-id="fb9a9-140">若要了解指定 C# 语言版本的其他方式，请参阅[选择 C# 语言版本](../configure-language-version.md)主题。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-140">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) topic.</span></span>
  
 <span data-ttu-id="fb9a9-141">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="fb9a9-141">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="fb9a9-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb9a9-142">See Also</span></span>  
 [<span data-ttu-id="fb9a9-143">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="fb9a9-143">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="fb9a9-144">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="fb9a9-144">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="fb9a9-145">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="fb9a9-145">C# Language Specification</span></span>

|<span data-ttu-id="fb9a9-146">版本</span><span class="sxs-lookup"><span data-stu-id="fb9a9-146">Version</span></span>|<span data-ttu-id="fb9a9-147">链接</span><span class="sxs-lookup"><span data-stu-id="fb9a9-147">Link</span></span>|<span data-ttu-id="fb9a9-148">描述</span><span class="sxs-lookup"><span data-stu-id="fb9a9-148">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="fb9a9-149">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="fb9a9-149">C# 1.0</span></span>|[<span data-ttu-id="fb9a9-150">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="fb9a9-150">Download DOC</span></span>](http://download.microsoft.com/download/a/9/e/a9e229b9-fee5-4c3e-8476-917dee385062/csharp%20language%20specification%20v1.0.doc)|<span data-ttu-id="fb9a9-151">C# 语言规范版本 1.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="fb9a9-151">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="fb9a9-152">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="fb9a9-152">C# 1.2</span></span>|[<span data-ttu-id="fb9a9-153">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="fb9a9-153">Download DOC</span></span>](http://download.microsoft.com/download/5/e/5/5e58be0a-b02b-41ac-a4a3-7a22286214ff/csharp%20language%20specification%20v1.2.doc)|<span data-ttu-id="fb9a9-154">C# 语言规范版本 1.2：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="fb9a9-154">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="fb9a9-155">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="fb9a9-155">C# 2.0</span></span>|[<span data-ttu-id="fb9a9-156">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="fb9a9-156">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/Ecma-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="fb9a9-157">标准 ECMA-334 第 4 版</span><span class="sxs-lookup"><span data-stu-id="fb9a9-157">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="fb9a9-158">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="fb9a9-158">C# 3.0</span></span>|[<span data-ttu-id="fb9a9-159">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="fb9a9-159">Download DOC</span></span>](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="fb9a9-160">C# 语言规范版本 3.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="fb9a9-160">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="fb9a9-161">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="fb9a9-161">C# 5.0</span></span>|[<span data-ttu-id="fb9a9-162">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="fb9a9-162">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf)|<span data-ttu-id="fb9a9-163">标准 ECMA-334 第 5 版</span><span class="sxs-lookup"><span data-stu-id="fb9a9-163">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="fb9a9-164">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="fb9a9-164">C# 6.0</span></span>|[<span data-ttu-id="fb9a9-165">链接</span><span class="sxs-lookup"><span data-stu-id="fb9a9-165">Link</span></span>](../language-specification/index.md)|<span data-ttu-id="fb9a9-166">C# 语言规范版本 6 - 非官方草稿：.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="fb9a9-166">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="fb9a9-167">C# 7.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="fb9a9-167">C# 7.0 and later</span></span>||<span data-ttu-id="fb9a9-168">当前不可用</span><span class="sxs-lookup"><span data-stu-id="fb9a9-168">not currently available</span></span>|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="fb9a9-169">支持所有语言功能所需的最低编译器版本</span><span class="sxs-lookup"><span data-stu-id="fb9a9-169">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="fb9a9-170">[↩](#TISO1)<a name="FISO1">ISO1</a>：Microsoft Visual Studio/生成工具 .Net 2002 或捆绑的 .Net Framework 1.0 编译器</span><span class="sxs-lookup"><span data-stu-id="fb9a9-170">[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="fb9a9-171">[↩](#TISO2)<a name="FISO2">ISO2</a>：Microsoft Visual Studio/生成工具 2005 或捆绑的 .Net Framework 2.0 编译器</span><span class="sxs-lookup"><span data-stu-id="fb9a9-171">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="fb9a9-172">[↩](#TCS3)<a name="FCS3">CS3</a>：Microsoft Visual Studio/生成工具 2008 或捆绑的 .Net Framework 3.5 编译器</span><span class="sxs-lookup"><span data-stu-id="fb9a9-172">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="fb9a9-173">[↩](#TCS4)<a name="FCS4">CS4</a>：Microsoft Visual Studio/生成工具 2010 或捆绑的 .Net Framework 4.0 编译器</span><span class="sxs-lookup"><span data-stu-id="fb9a9-173">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="fb9a9-174">[↩](#TCS5)<a name="FCS5">CS5</a>：Microsoft Visual Studio/生成工具 2012 或捆绑的 .Net Framework 4.5 编译器</span><span class="sxs-lookup"><span data-stu-id="fb9a9-174">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="fb9a9-175">[↩](#TCS6)<a name="FCS6">CS6</a>：Microsoft Visual Studio/生成工具 2015</span><span class="sxs-lookup"><span data-stu-id="fb9a9-175">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="fb9a9-176">[↩](#TCS7)<a name="FCS7">CS7</a>：Microsoft Visual Studio/生成工具 2017</span><span class="sxs-lookup"><span data-stu-id="fb9a9-176">[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   
<span data-ttu-id="fb9a9-177">[↩](#TCS71)<a name="FCS71">CS71</a>：Microsoft Visual Studio/生成工具 2017，版本 15.3</span><span class="sxs-lookup"><span data-stu-id="fb9a9-177">[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>    
<span data-ttu-id="fb9a9-178">[↩](#TCS72)<a name="FCS72">CS72</a>：Microsoft Visual Studio/生成工具 2017，版本 15.5</span><span class="sxs-lookup"><span data-stu-id="fb9a9-178">[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>    
<span data-ttu-id="fb9a9-179">[↩](#TCS73)<a name="FCS73">CS73</a>：Microsoft Visual Studio/生成工具 2017，版本 15.7</span><span class="sxs-lookup"><span data-stu-id="fb9a9-179">[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>    

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS8)<a name="FCS8">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
