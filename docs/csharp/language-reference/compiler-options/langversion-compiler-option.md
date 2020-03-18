---
title: -langversion（C# 编译器选项）
ms.date: 08/23/2019
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
ms.openlocfilehash: 007b10f6f27233c43caad4c1910e3d1158682950
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76920369"
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="1fce7-102">-langversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="1fce7-102">-langversion (C# Compiler Options)</span></span>

<span data-ttu-id="1fce7-103">使编译器仅接受包含在所选 C# 语言规范中的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fce7-104">语法</span><span class="sxs-lookup"><span data-stu-id="1fce7-104">Syntax</span></span>

```console
-langversion:option
```

## <a name="arguments"></a><span data-ttu-id="1fce7-105">参数</span><span class="sxs-lookup"><span data-stu-id="1fce7-105">Arguments</span></span>

`option`

<span data-ttu-id="1fce7-106">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="1fce7-106">The following values are valid:</span></span>

|<span data-ttu-id="1fce7-107">选项</span><span class="sxs-lookup"><span data-stu-id="1fce7-107">Option</span></span>|<span data-ttu-id="1fce7-108">含义</span><span class="sxs-lookup"><span data-stu-id="1fce7-108">Meaning</span></span>|
|------------|-------------|
|<span data-ttu-id="1fce7-109">preview</span><span class="sxs-lookup"><span data-stu-id="1fce7-109">preview</span></span>|<span data-ttu-id="1fce7-110">编译器接受它可支持的最新预览版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-110">The compiler accepts all valid language syntax from the latest preview version that it can support.</span></span>|
|<span data-ttu-id="1fce7-111">最新</span><span class="sxs-lookup"><span data-stu-id="1fce7-111">latest</span></span>|<span data-ttu-id="1fce7-112">编译器接受它可支持的最新版本（包括次要版本）中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-112">The compiler accepts all valid language syntax from the latest version (including minor releases) that it can support.</span></span>|
|<span data-ttu-id="1fce7-113">latestMajor</span><span class="sxs-lookup"><span data-stu-id="1fce7-113">latestMajor</span></span>|<span data-ttu-id="1fce7-114">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-114">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="1fce7-115">8.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-115">8.0</span></span>|<span data-ttu-id="1fce7-116">编译器只接受 C# 8.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-116">The compiler accepts only syntax that is included in C# 8.0 or lower.</span></span>|
|<span data-ttu-id="1fce7-117">7.3</span><span class="sxs-lookup"><span data-stu-id="1fce7-117">7.3</span></span>|<span data-ttu-id="1fce7-118">编译器只接受 C# 7.3 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-118">The compiler accepts only syntax that is included in C# 7.3 or lower.</span></span>|
|<span data-ttu-id="1fce7-119">7.2</span><span class="sxs-lookup"><span data-stu-id="1fce7-119">7.2</span></span>|<span data-ttu-id="1fce7-120">编译器只接受 C# 7.2 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-120">The compiler accepts only syntax that is included in C# 7.2 or lower.</span></span>|
|<span data-ttu-id="1fce7-121">7.1</span><span class="sxs-lookup"><span data-stu-id="1fce7-121">7.1</span></span>|<span data-ttu-id="1fce7-122">编译器只接受 C# 7.1 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-122">The compiler accepts only syntax that is included in C# 7.1 or lower.</span></span>|
|<span data-ttu-id="1fce7-123">7</span><span class="sxs-lookup"><span data-stu-id="1fce7-123">7</span></span>|<span data-ttu-id="1fce7-124">编译器只接受 C# 7.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-124">The compiler accepts only syntax that is included in C# 7.0 or lower.</span></span>|
|<span data-ttu-id="1fce7-125">6</span><span class="sxs-lookup"><span data-stu-id="1fce7-125">6</span></span>|<span data-ttu-id="1fce7-126">编译器只接受 C# 6.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-126">The compiler accepts only syntax that is included in C# 6.0 or lower.</span></span>|
|<span data-ttu-id="1fce7-127">5</span><span class="sxs-lookup"><span data-stu-id="1fce7-127">5</span></span>|<span data-ttu-id="1fce7-128">编译器只接受 C# 5.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-128">The compiler accepts only syntax that is included in C# 5.0 or lower.</span></span>|
|<span data-ttu-id="1fce7-129">4</span><span class="sxs-lookup"><span data-stu-id="1fce7-129">4</span></span>|<span data-ttu-id="1fce7-130">编译器只接受 C# 4.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-130">The compiler accepts only syntax that is included in C# 4.0 or lower.</span></span>|
|<span data-ttu-id="1fce7-131">3</span><span class="sxs-lookup"><span data-stu-id="1fce7-131">3</span></span>|<span data-ttu-id="1fce7-132">编译器只接受 C# 3.0 或更低版本中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-132">The compiler accepts only syntax that is included in C# 3.0 or lower.</span></span>|
|<span data-ttu-id="1fce7-133">ISO-2</span><span class="sxs-lookup"><span data-stu-id="1fce7-133">ISO-2</span></span>|<span data-ttu-id="1fce7-134">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-134">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0).</span></span>|
|<span data-ttu-id="1fce7-135">ISO-1</span><span class="sxs-lookup"><span data-stu-id="1fce7-135">ISO-1</span></span>|<span data-ttu-id="1fce7-136">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法。</span><span class="sxs-lookup"><span data-stu-id="1fce7-136">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2).</span></span>|

<span data-ttu-id="1fce7-137">默认语言版本依赖于应用程序的目标框架以及所安装的 SDK 或 Visual Studio 的版本。</span><span class="sxs-lookup"><span data-stu-id="1fce7-137">The default language version depends on the target framework for your application and the version of the SDK or Visual Studio installed.</span></span> <span data-ttu-id="1fce7-138">有关这些规则的定义，请参见[配置语言版本](../configure-language-version.md#defaults)一文。</span><span class="sxs-lookup"><span data-stu-id="1fce7-138">Those rules are defined in the [configuring the language version](../configure-language-version.md#defaults) article.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fce7-139">备注</span><span class="sxs-lookup"><span data-stu-id="1fce7-139">Remarks</span></span>

<span data-ttu-id="1fce7-140">C# 应用程序引用的元数据不受 -langversion 编译器选项约束  。</span><span class="sxs-lookup"><span data-stu-id="1fce7-140">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>

<span data-ttu-id="1fce7-141">每个版本的 C# 编译器都包含语言规范的扩展，因此 -langversion 不提供早期版本编译器的同等功能  。</span><span class="sxs-lookup"><span data-stu-id="1fce7-141">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>

<span data-ttu-id="1fce7-142">此外，虽然 C# 版本更新通常与主要的 .NET Framework 版本一致，但新的语法和功能不一定绑定到该特定的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="1fce7-142">Additionally, while C# version updates generally coincide with major .NET Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="1fce7-143">虽然新功能肯定需要与 C# 修订版一起发布的新编译器更新，但每项具体功能都有自己的最小 .NET API 或公共语言运行时要求，这些要求通过包括 NuGet 包或其他库允许功能在下层框架上运行。</span><span class="sxs-lookup"><span data-stu-id="1fce7-143">While the new features definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .NET API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>

<span data-ttu-id="1fce7-144">无论使用哪一项 -langversion  设置，请使用当前版本的公共语言运行时来创建 .exe 或 .dll。</span><span class="sxs-lookup"><span data-stu-id="1fce7-144">Regardless of which **-langversion** setting you use, use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="1fce7-145">友元程序集和 [-moduleassemblyname（C# 编译器选项）](./moduleassemblyname-compiler-option.md)是一个例外，它们在 -langversion:ISO-1 下工作  。</span><span class="sxs-lookup"><span data-stu-id="1fce7-145">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](./moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>

<span data-ttu-id="1fce7-146">如需了解指定 C# 语言版本的其他方式，请参阅[选择 C# 语言版本](../configure-language-version.md)一文。</span><span class="sxs-lookup"><span data-stu-id="1fce7-146">For other ways to specify the C# language version, see the [Select the C# language version](../configure-language-version.md) article.</span></span>

<span data-ttu-id="1fce7-147">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="1fce7-147">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1fce7-148">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1fce7-148">C# language specification</span></span>

|<span data-ttu-id="1fce7-149">Version</span><span class="sxs-lookup"><span data-stu-id="1fce7-149">Version</span></span>|<span data-ttu-id="1fce7-150">链接</span><span class="sxs-lookup"><span data-stu-id="1fce7-150">Link</span></span>|<span data-ttu-id="1fce7-151">说明</span><span class="sxs-lookup"><span data-stu-id="1fce7-151">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="1fce7-152">C# 7.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="1fce7-152">C# 7.0 and later</span></span>||<span data-ttu-id="1fce7-153">当前不可用</span><span class="sxs-lookup"><span data-stu-id="1fce7-153">not currently available</span></span>|
|<span data-ttu-id="1fce7-154">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-154">C# 6.0</span></span>|[<span data-ttu-id="1fce7-155">链接</span><span class="sxs-lookup"><span data-stu-id="1fce7-155">Link</span></span>](/dotnet/csharp/language-reference/language-specification/introduction)|<span data-ttu-id="1fce7-156">C# 语言规范版本 6 - 非官方草稿：.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="1fce7-156">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="1fce7-157">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-157">C# 5.0</span></span>|[<span data-ttu-id="1fce7-158">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="1fce7-158">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/ECMA-334.pdf)|<span data-ttu-id="1fce7-159">标准 ECMA-334 第 5 版</span><span class="sxs-lookup"><span data-stu-id="1fce7-159">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="1fce7-160">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-160">C# 3.0</span></span>|[<span data-ttu-id="1fce7-161">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="1fce7-161">Download DOC</span></span>](https://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="1fce7-162">C# 语言规范版本 3.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1fce7-162">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="1fce7-163">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-163">C# 2.0</span></span>|[<span data-ttu-id="1fce7-164">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="1fce7-164">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="1fce7-165">标准 ECMA-334 第 4 版</span><span class="sxs-lookup"><span data-stu-id="1fce7-165">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="1fce7-166">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="1fce7-166">C# 1.2</span></span>|[<span data-ttu-id="1fce7-167">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="1fce7-167">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%202nd%20edition%20December%202002.pdf)|<span data-ttu-id="1fce7-168">C# 语言规范版本 1.2：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1fce7-168">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="1fce7-169">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-169">C# 1.0</span></span>|[<span data-ttu-id="1fce7-170">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="1fce7-170">Download DOC</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-334%201st%20edition%20December%202001.pdf)|<span data-ttu-id="1fce7-171">C# 语言规范版本 1.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="1fce7-171">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|

## <a name="minimum-sdk-version-needed-to-support-all-language-features"></a><span data-ttu-id="1fce7-172">支持所有语言功能所需的最低 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="1fce7-172">Minimum SDK version needed to support all language features</span></span>

<span data-ttu-id="1fce7-173">下表列出了支持相应语言版本的 C# 编译器的 SDK 的最低版本：</span><span class="sxs-lookup"><span data-stu-id="1fce7-173">The following table lists the minimum versions of the SDK with the C# compiler that supports the corresponding language version:</span></span>

|<span data-ttu-id="1fce7-174">C# 版本</span><span class="sxs-lookup"><span data-stu-id="1fce7-174">C# version</span></span>|<span data-ttu-id="1fce7-175">最低 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="1fce7-175">Minimum SDK version</span></span>|
|----------|-------------------|
|<span data-ttu-id="1fce7-176">C# 8.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-176">C# 8.0</span></span>| <span data-ttu-id="1fce7-177">Microsoft Visual Studio/生成工具 2019，版本 16.3 或 .NET Core 3.0 SDK</span><span class="sxs-lookup"><span data-stu-id="1fce7-177">Microsoft Visual Studio/Build Tools 2019, version 16.3, or .NET Core 3.0 SDK</span></span> |
|<span data-ttu-id="1fce7-178">C# 7.3</span><span class="sxs-lookup"><span data-stu-id="1fce7-178">C# 7.3</span></span>| <span data-ttu-id="1fce7-179">Microsoft Visual Studio/生成工具 2017，版本 15.7</span><span class="sxs-lookup"><span data-stu-id="1fce7-179">Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span> |
|<span data-ttu-id="1fce7-180">C# 7.2</span><span class="sxs-lookup"><span data-stu-id="1fce7-180">C# 7.2</span></span>| <span data-ttu-id="1fce7-181">Microsoft Visual Studio/生成工具 2017，版本 15.5</span><span class="sxs-lookup"><span data-stu-id="1fce7-181">Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span> |
|<span data-ttu-id="1fce7-182">C# 7.1</span><span class="sxs-lookup"><span data-stu-id="1fce7-182">C# 7.1</span></span>| <span data-ttu-id="1fce7-183">Microsoft Visual Studio/生成工具 2017，版本 15.3</span><span class="sxs-lookup"><span data-stu-id="1fce7-183">Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span> |
|<span data-ttu-id="1fce7-184">C# 7.0</span><span class="sxs-lookup"><span data-stu-id="1fce7-184">C# 7.0</span></span>| <span data-ttu-id="1fce7-185">Microsoft Visual Studio/生成工具 2017</span><span class="sxs-lookup"><span data-stu-id="1fce7-185">Microsoft Visual Studio/Build Tools 2017</span></span> |
|<span data-ttu-id="1fce7-186">C# 6</span><span class="sxs-lookup"><span data-stu-id="1fce7-186">C# 6</span></span>| <span data-ttu-id="1fce7-187">Microsoft Visual Studio/生成工具 2015</span><span class="sxs-lookup"><span data-stu-id="1fce7-187">Microsoft Visual Studio/Build Tools 2015</span></span> |
|<span data-ttu-id="1fce7-188">C# 5</span><span class="sxs-lookup"><span data-stu-id="1fce7-188">C# 5</span></span>| <span data-ttu-id="1fce7-189">Microsoft Visual Studio/生成工具 2012 或捆绑的 .NET Framework 4.5 编译器</span><span class="sxs-lookup"><span data-stu-id="1fce7-189">Microsoft Visual Studio/Build Tools 2012 or bundled .NET Framework 4.5 compiler</span></span> |
|<span data-ttu-id="1fce7-190">C# 4</span><span class="sxs-lookup"><span data-stu-id="1fce7-190">C# 4</span></span>| <span data-ttu-id="1fce7-191">Microsoft Visual Studio/生成工具 2010 或捆绑的 .NET Framework 4.0 编译器</span><span class="sxs-lookup"><span data-stu-id="1fce7-191">Microsoft Visual Studio/Build Tools 2010 or bundled .NET Framework 4.0 compiler</span></span> |
|<span data-ttu-id="1fce7-192">C# 3</span><span class="sxs-lookup"><span data-stu-id="1fce7-192">C# 3</span></span>| <span data-ttu-id="1fce7-193">Microsoft Visual Studio/生成工具 2008 或捆绑的 .NET Framework 3.5 编译器</span><span class="sxs-lookup"><span data-stu-id="1fce7-193">Microsoft Visual Studio/Build Tools 2008 or bundled .NET Framework 3.5 compiler</span></span> |
|<span data-ttu-id="1fce7-194">C# 2</span><span class="sxs-lookup"><span data-stu-id="1fce7-194">C# 2</span></span>| <span data-ttu-id="1fce7-195">Microsoft Visual Studio/生成工具 2005 或捆绑的 .Net Framework 2.0 编译器</span><span class="sxs-lookup"><span data-stu-id="1fce7-195">Microsoft Visual Studio/Build Tools 2005 or bundled .NET Framework 2.0 compiler</span></span> |
|<span data-ttu-id="1fce7-196">C# 1.0/1.2</span><span class="sxs-lookup"><span data-stu-id="1fce7-196">C# 1.0/1.2</span></span> | <span data-ttu-id="1fce7-197">Microsoft Visual Studio/生成工具 .NET 2002 或捆绑的 .NET Framework 1.0 编译器</span><span class="sxs-lookup"><span data-stu-id="1fce7-197">Microsoft Visual Studio/Build Tools .NET 2002 or bundled .NET Framework 1.0 compiler</span></span> |

## <a name="see-also"></a><span data-ttu-id="1fce7-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fce7-198">See also</span></span>

- [<span data-ttu-id="1fce7-199">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="1fce7-199">C# Compiler Options</span></span>](index.md)
- [<span data-ttu-id="1fce7-200">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="1fce7-200">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
