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
ms.openlocfilehash: 030af5df222772b1e5a4d6f6946e59f4f2d1e1a9
ms.sourcegitcommit: 96543603ae29bc05cecccb8667974d058af63b4a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2019
ms.locfileid: "66195802"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="6bc36-102">-langversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="6bc36-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="6bc36-103">使编译器仅接受包含在所选 C# 语言规范中的语法。</span><span class="sxs-lookup"><span data-stu-id="6bc36-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bc36-104">语法</span><span class="sxs-lookup"><span data-stu-id="6bc36-104">Syntax</span></span>  

```console
-langversion:option  
```

## <a name="arguments"></a><span data-ttu-id="6bc36-105">自变量</span><span class="sxs-lookup"><span data-stu-id="6bc36-105">Arguments</span></span>

 `option`  
 <span data-ttu-id="6bc36-106">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="6bc36-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="6bc36-107">选项</span><span class="sxs-lookup"><span data-stu-id="6bc36-107">Option</span></span>|<span data-ttu-id="6bc36-108">含义</span><span class="sxs-lookup"><span data-stu-id="6bc36-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="6bc36-109">preview</span><span class="sxs-lookup"><span data-stu-id="6bc36-109">preview</span></span>|<span data-ttu-id="6bc36-110">编译器接受它可支持的最新预览版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="6bc36-110">The compiler accepts all valid language syntax from the latest preview version that it can support.</span></span>|
|<span data-ttu-id="6bc36-111">最新</span><span class="sxs-lookup"><span data-stu-id="6bc36-111">latest</span></span>|<span data-ttu-id="6bc36-112">编译器接受它可支持的最新版本（包括次要版本）中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="6bc36-112">The compiler accepts all valid language syntax from the latest version (including minor releases) that it can support.</span></span>|
|<span data-ttu-id="6bc36-113">latestMajor</span><span class="sxs-lookup"><span data-stu-id="6bc36-113">latestMajor</span></span>|<span data-ttu-id="6bc36-114">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="6bc36-114">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="6bc36-115">8.0</span><span class="sxs-lookup"><span data-stu-id="6bc36-115">8.0</span></span>|<span data-ttu-id="6bc36-116">编译器只接受 C# 8.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="6bc36-116">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span> <span data-ttu-id="6bc36-117"><sup id="TCS80">[CS80](#FCS80)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-117"><sup id="TCS80">[CS80](#FCS80)</sup></span></span>|
|<span data-ttu-id="6bc36-118">7.3</span><span class="sxs-lookup"><span data-stu-id="6bc36-118">7.3</span></span>|<span data-ttu-id="6bc36-119">编译器只接受 C# 7.3 或更低版本中所含的语法 <sup id="TCS73">[CS73](#FCS73)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-119">The compiler accepts only syntax that is included in C# 7.3 or lower <sup id="TCS73">[CS73](#FCS73)</sup></span></span>|
|<span data-ttu-id="6bc36-120">7.2</span><span class="sxs-lookup"><span data-stu-id="6bc36-120">7.2</span></span>|<span data-ttu-id="6bc36-121">编译器只接受 C# 7.2 或更低版本中所含的语法 <sup id="TCS72">[CS72](#FCS72)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-121">The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS72">[CS72](#FCS72)</sup></span></span>|
|<span data-ttu-id="6bc36-122">7.1</span><span class="sxs-lookup"><span data-stu-id="6bc36-122">7.1</span></span>|<span data-ttu-id="6bc36-123">编译器只接受 C# 7.1 或更低版本中所含的语法 <sup id="TCS71">[CS71](#FCS71)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-123">The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup></span></span>|
|<span data-ttu-id="6bc36-124">7</span><span class="sxs-lookup"><span data-stu-id="6bc36-124">7</span></span>|<span data-ttu-id="6bc36-125">编译器只接受 C# 7.0 或更低版本中所含的语法 <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-125">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="6bc36-126">6</span><span class="sxs-lookup"><span data-stu-id="6bc36-126">6</span></span>|<span data-ttu-id="6bc36-127">编译器只接受 C# 6.0 或更低版本中所含的语法 <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-127">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="6bc36-128">5</span><span class="sxs-lookup"><span data-stu-id="6bc36-128">5</span></span>|<span data-ttu-id="6bc36-129">编译器只接受 C# 5.0 或更低版本中所含的语法 <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-129">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="6bc36-130">4</span><span class="sxs-lookup"><span data-stu-id="6bc36-130">4</span></span>|<span data-ttu-id="6bc36-131">编译器只接受 C# 4.0 或更低版本中所含的语法 <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-131">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="6bc36-132">3</span><span class="sxs-lookup"><span data-stu-id="6bc36-132">3</span></span>|<span data-ttu-id="6bc36-133">编译器只接受 C# 3.0 或更低版本中所含的语法 <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-133">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="6bc36-134">ISO-2</span><span class="sxs-lookup"><span data-stu-id="6bc36-134">ISO-2</span></span>|<span data-ttu-id="6bc36-135">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法 <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-135">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="6bc36-136">ISO-1</span><span class="sxs-lookup"><span data-stu-id="6bc36-136">ISO-1</span></span>|<span data-ttu-id="6bc36-137">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法 <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="6bc36-137">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  

## <a name="remarks"></a><span data-ttu-id="6bc36-138">备注</span><span class="sxs-lookup"><span data-stu-id="6bc36-138">Remarks</span></span>

 <span data-ttu-id="6bc36-139">C# 应用程序引用的元数据不受 -langversion 编译器选项约束。</span><span class="sxs-lookup"><span data-stu-id="6bc36-139">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="6bc36-140">每个版本的 C# 编译器都包含语言规范的扩展，因此 -langversion 不提供早期版本编译器的同等功能。</span><span class="sxs-lookup"><span data-stu-id="6bc36-140">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  

 <span data-ttu-id="6bc36-141">此外，虽然 C# 版本更新通常与主要的 .NET Framework 版本一致，但新的语法和功能不一定绑定到该特定的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="6bc36-141">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="6bc36-142">虽然新功能肯定需要与 C# 修订版一起发布的新编译器更新，但每项具体功能都有自己的最小 .NET API 或公共语言运行时要求，这些要求通过包括 NuGet 包或其他库允许功能在下层框架上运行。</span><span class="sxs-lookup"><span data-stu-id="6bc36-142">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="6bc36-143">无论使用哪一项 -langversion 设置，都将使用当前版本的公共语言运行时来创建 .exe 或 .dll。</span><span class="sxs-lookup"><span data-stu-id="6bc36-143">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="6bc36-144">友元程序集和 [-moduleassemblyname（C# 编译器选项）](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)是一个例外，它们在 -langversion:ISO-1 下工作。</span><span class="sxs-lookup"><span data-stu-id="6bc36-144">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  

 <span data-ttu-id="6bc36-145">若要了解指定 C# 语言版本的其他方式，请参阅[选择 C# 语言版本](../configure-language-version.md)主题。</span><span class="sxs-lookup"><span data-stu-id="6bc36-145">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) topic.</span></span>
  
 <span data-ttu-id="6bc36-146">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="6bc36-146">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  

## <a name="see-also"></a><span data-ttu-id="6bc36-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="6bc36-147">See also</span></span>

- [<span data-ttu-id="6bc36-148">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="6bc36-148">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="6bc36-149">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="6bc36-149">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

### <a name="c-language-specification"></a><span data-ttu-id="6bc36-150">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="6bc36-150">C# Language Specification</span></span>

|<span data-ttu-id="6bc36-151">Version</span><span class="sxs-lookup"><span data-stu-id="6bc36-151">Version</span></span>|<span data-ttu-id="6bc36-152">链接</span><span class="sxs-lookup"><span data-stu-id="6bc36-152">Link</span></span>|<span data-ttu-id="6bc36-153">说明</span><span class="sxs-lookup"><span data-stu-id="6bc36-153">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="6bc36-154">C# 7.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="6bc36-154">C# 7.0 and later</span></span>||<span data-ttu-id="6bc36-155">当前不可用</span><span class="sxs-lookup"><span data-stu-id="6bc36-155">not currently available</span></span>|
|<span data-ttu-id="6bc36-156">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="6bc36-156">C# 6.0</span></span>|[<span data-ttu-id="6bc36-157">链接</span><span class="sxs-lookup"><span data-stu-id="6bc36-157">Link</span></span>](../language-specification/index.md)|<span data-ttu-id="6bc36-158">C# 语言规范版本 6 - 非官方草稿：.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="6bc36-158">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="6bc36-159">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="6bc36-159">C# 5.0</span></span>|[<span data-ttu-id="6bc36-160">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="6bc36-160">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|<span data-ttu-id="6bc36-161">标准 ECMA-334 第 5 版</span><span class="sxs-lookup"><span data-stu-id="6bc36-161">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="6bc36-162">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="6bc36-162">C# 3.0</span></span>|[<span data-ttu-id="6bc36-163">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="6bc36-163">Download DOC</span></span>](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="6bc36-164">C# 语言规范版本 3.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="6bc36-164">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="6bc36-165">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="6bc36-165">C# 2.0</span></span>|[<span data-ttu-id="6bc36-166">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="6bc36-166">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="6bc36-167">标准 ECMA-334 第 4 版</span><span class="sxs-lookup"><span data-stu-id="6bc36-167">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="6bc36-168">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="6bc36-168">C# 1.2</span></span>|[<span data-ttu-id="6bc36-169">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="6bc36-169">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|<span data-ttu-id="6bc36-170">C# 语言规范版本 1.2：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="6bc36-170">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="6bc36-171">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="6bc36-171">C# 1.0</span></span>|[<span data-ttu-id="6bc36-172">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="6bc36-172">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|<span data-ttu-id="6bc36-173">C# 语言规范版本 1.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="6bc36-173">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="6bc36-174">支持所有语言功能所需的最低编译器版本</span><span class="sxs-lookup"><span data-stu-id="6bc36-174">Minimum compiler version needed to support all language features</span></span>

<span data-ttu-id="6bc36-175">[↩](#TCS80)<a name="FCS80">CS80</a>：Microsoft Visual Studio/生成工具 2019，版本 16 或 .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="6bc36-175">[↩](#TCS80)<a name="FCS80">CS80</a>: Microsoft Visual Studio/Build Tools 2019, version 16, or .NET Core 3.0 SDK</span></span>  
<span data-ttu-id="6bc36-176">[↩](#TCS73)<a name="FCS73">CS73</a>：Microsoft Visual Studio/生成工具 2017，版本 15.7</span><span class="sxs-lookup"><span data-stu-id="6bc36-176">[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>  
<span data-ttu-id="6bc36-177">[↩](#TCS72)<a name="FCS72">CS72</a>：Microsoft Visual Studio/生成工具 2017，版本 15.5</span><span class="sxs-lookup"><span data-stu-id="6bc36-177">[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>  
<span data-ttu-id="6bc36-178">[↩](#TCS71)<a name="FCS71">CS71</a>：Microsoft Visual Studio/生成工具 2017，版本 15.3</span><span class="sxs-lookup"><span data-stu-id="6bc36-178">[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>  
<span data-ttu-id="6bc36-179">[↩](#TCS7)<a name="FCS7">CS7</a>：Microsoft Visual Studio/生成工具 2017</span><span class="sxs-lookup"><span data-stu-id="6bc36-179">[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017</span></span>  
<span data-ttu-id="6bc36-180">[↩](#TCS6)<a name="FCS6">CS6</a>：Microsoft Visual Studio/生成工具 2015</span><span class="sxs-lookup"><span data-stu-id="6bc36-180">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>  
<span data-ttu-id="6bc36-181">[↩](#TCS5)<a name="FCS5">CS5</a>：Microsoft Visual Studio/生成工具 2012 或捆绑的 .NET Framework 4.5 编译器</span><span class="sxs-lookup"><span data-stu-id="6bc36-181">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span>  
<span data-ttu-id="6bc36-182">[↩](#TCS4)<a name="FCS4">CS4</a>：Microsoft Visual Studio/生成工具 2010 或捆绑的 .NET Framework 4.0 编译器</span><span class="sxs-lookup"><span data-stu-id="6bc36-182">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span>  
<span data-ttu-id="6bc36-183">[↩](#TCS3)<a name="FCS3">CS3</a>：Microsoft Visual Studio/生成工具 2008 或捆绑的 .NET Framework 3.5 编译器</span><span class="sxs-lookup"><span data-stu-id="6bc36-183">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span>  
<span data-ttu-id="6bc36-184">[↩](#TISO2)<a name="FISO2">ISO2</a>：Microsoft Visual Studio/生成工具 2005 或捆绑的 .Net Framework 2.0 编译器</span><span class="sxs-lookup"><span data-stu-id="6bc36-184">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span>  
<span data-ttu-id="6bc36-185">[↩](#TISO1)<a name="FISO1">ISO1</a>：Microsoft Visual Studio/生成工具 .NET 2002 或捆绑的 .Net Framework 1.0 编译器</span><span class="sxs-lookup"><span data-stu-id="6bc36-185">[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .NET 2002 or bundled .N Framework 1.0 compiler</span></span>  
