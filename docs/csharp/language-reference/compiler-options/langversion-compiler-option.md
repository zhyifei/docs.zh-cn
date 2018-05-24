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
ms.openlocfilehash: 299ff121bab87482b7cdcaebc8b43cb8a1b559ec
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="8f2b4-102">-langversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="8f2b4-102">-langversion (C# Compiler Options)</span></span>
<span data-ttu-id="8f2b4-103">使编译器仅接受包含在所选 C# 语言规范中的语法。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f2b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="8f2b4-104">Syntax</span></span>  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="8f2b4-105">自变量</span><span class="sxs-lookup"><span data-stu-id="8f2b4-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="8f2b4-106">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="8f2b4-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="8f2b4-107">选项</span><span class="sxs-lookup"><span data-stu-id="8f2b4-107">Option</span></span>|<span data-ttu-id="8f2b4-108">含义</span><span class="sxs-lookup"><span data-stu-id="8f2b4-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="8f2b4-109">default</span><span class="sxs-lookup"><span data-stu-id="8f2b4-109">default</span></span>|<span data-ttu-id="8f2b4-110">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-110">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span>|
|<span data-ttu-id="8f2b4-111">ISO-1</span><span class="sxs-lookup"><span data-stu-id="8f2b4-111">ISO-1</span></span>|<span data-ttu-id="8f2b4-112">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.2) 中所含的语法 <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-112">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.2) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="8f2b4-113">ISO-2</span><span class="sxs-lookup"><span data-stu-id="8f2b4-113">ISO-2</span></span>|<span data-ttu-id="8f2b4-114">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法 <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-114">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="8f2b4-115">3</span><span class="sxs-lookup"><span data-stu-id="8f2b4-115">3</span></span>|<span data-ttu-id="8f2b4-116">编译器只接受 C# 3.0 或更低版本中所含的语法 <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-116">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="8f2b4-117">4</span><span class="sxs-lookup"><span data-stu-id="8f2b4-117">4</span></span>|<span data-ttu-id="8f2b4-118">编译器只接受 C# 4.0 或更低版本中所含的语法 <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-118">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="8f2b4-119">5</span><span class="sxs-lookup"><span data-stu-id="8f2b4-119">5</span></span>|<span data-ttu-id="8f2b4-120">编译器只接受 C# 5.0 或更低版本中所含的语法 <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-120">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="8f2b4-121">6</span><span class="sxs-lookup"><span data-stu-id="8f2b4-121">6</span></span>|<span data-ttu-id="8f2b4-122">编译器只接受 C# 6.0 或更低版本中所含的语法 <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-122">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="8f2b4-123">7</span><span class="sxs-lookup"><span data-stu-id="8f2b4-123">7</span></span>|<span data-ttu-id="8f2b4-124">编译器只接受 C# 7.0 或更低版本中所含的语法 <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-124">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="8f2b4-125">7.1</span><span class="sxs-lookup"><span data-stu-id="8f2b4-125">7.1</span></span>|<span data-ttu-id="8f2b4-126">编译器只接受 C# 7.1 或更低版本中所含的语法 <sup id="TCS71">[CS71](#FCS71)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-126">The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup></span></span>|
|<span data-ttu-id="8f2b4-127">7.2</span><span class="sxs-lookup"><span data-stu-id="8f2b4-127">7.2</span></span>|<span data-ttu-id="8f2b4-128">编译器只接受 C# 7.2 或更低版本中所含的语法 <sup id="TCS72">[CS72](#FCS72)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-128">The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS72">[CS72](#FCS72)</sup></span></span>|
|<span data-ttu-id="8f2b4-129">7.3</span><span class="sxs-lookup"><span data-stu-id="8f2b4-129">7.3</span></span>|<span data-ttu-id="8f2b4-130">编译器只接受 C# 7.3 或更低版本中所含的语法 <sup id="TCS73">[CS73](#FCS73)</sup></span><span class="sxs-lookup"><span data-stu-id="8f2b4-130">The compiler accepts only syntax that is included in C# 7.3 or lower <sup id="TCS73">[CS73](#FCS73)</sup></span></span>|
|<span data-ttu-id="8f2b4-131">最新</span><span class="sxs-lookup"><span data-stu-id="8f2b4-131">latest</span></span>|<span data-ttu-id="8f2b4-132">编译器接受它可支持的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-132">The compiler accepts all valid language syntax that it can support.</span></span>|

<!--- Uncomment and move these above
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS8">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="8f2b4-133">备注</span><span class="sxs-lookup"><span data-stu-id="8f2b4-133">Remarks</span></span>  
 <span data-ttu-id="8f2b4-134">C# 应用程序引用的元数据不受 -langversion 编译器选项约束。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-134">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="8f2b4-135">每个版本的 C# 编译器都包含语言规范的扩展，因此 -langversion 不提供早期版本编译器的同等功能。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-135">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="8f2b4-136">此外，虽然 C# 版本更新通常与主要的 .Net Framework 版本一致，但新的语法和功能不一定绑定到该特定的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-136">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="8f2b4-137">虽然新功能肯定会需要与 C# 修订版一起发布的新编译器更新，但每项具体功能都有自己的最小 .Net API 或公共语言运行时要求，这些要求通过包括 NuGet 包或其他库允许功能本身在下层框架上运行。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-137">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="8f2b4-138">无论使用哪一项 -langversion 设置，都将使用当前版本的公共语言运行时来创建 .exe 或 .dll。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-138">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="8f2b4-139">友元程序集和 [-moduleassemblyname（C# 编译器选项）](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)是一个例外，它们在 -langversion:ISO-1 下工作。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-139">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="8f2b4-140">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="8f2b4-140">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="8f2b4-141">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-141">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="8f2b4-142">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-142">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="8f2b4-143">单击“高级”按钮。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-143">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="8f2b4-144">修改“语言版本”属性。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-144">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="8f2b4-145">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="8f2b4-145">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="8f2b4-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f2b4-146">See Also</span></span>  
 [<span data-ttu-id="8f2b4-147">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="8f2b4-147">C# Compiler Options</span></span>](index.md)  
 [<span data-ttu-id="8f2b4-148">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="8f2b4-148">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="8f2b4-149">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8f2b4-149">C# Language Specification</span></span>

|<span data-ttu-id="8f2b4-150">版本</span><span class="sxs-lookup"><span data-stu-id="8f2b4-150">Version</span></span>|<span data-ttu-id="8f2b4-151">链接</span><span class="sxs-lookup"><span data-stu-id="8f2b4-151">Link</span></span>|<span data-ttu-id="8f2b4-152">描述</span><span class="sxs-lookup"><span data-stu-id="8f2b4-152">Description</span></span>|
|-------|----|-----------|
|<span data-ttu-id="8f2b4-153">C# 1.0</span><span class="sxs-lookup"><span data-stu-id="8f2b4-153">C# 1.0</span></span>|[<span data-ttu-id="8f2b4-154">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="8f2b4-154">Download DOC</span></span>](http://download.microsoft.com/download/a/9/e/a9e229b9-fee5-4c3e-8476-917dee385062/csharp%20language%20specification%20v1.0.doc)|<span data-ttu-id="8f2b4-155">C# 语言规范版本 1.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="8f2b4-155">C# Language Specification Version 1.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="8f2b4-156">C# 1.2</span><span class="sxs-lookup"><span data-stu-id="8f2b4-156">C# 1.2</span></span>|[<span data-ttu-id="8f2b4-157">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="8f2b4-157">Download DOC</span></span>](http://download.microsoft.com/download/5/e/5/5e58be0a-b02b-41ac-a4a3-7a22286214ff/csharp%20language%20specification%20v1.2.doc)|<span data-ttu-id="8f2b4-158">C# 语言规范版本 1.2：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="8f2b4-158">C# Language Specification Version 1.2: Microsoft Corporation</span></span>|
|<span data-ttu-id="8f2b4-159">C# 2.0</span><span class="sxs-lookup"><span data-stu-id="8f2b4-159">C# 2.0</span></span>|[<span data-ttu-id="8f2b4-160">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="8f2b4-160">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/Ecma-334%204th%20edition%20June%202006.pdf)|<span data-ttu-id="8f2b4-161">标准 ECMA-334 第 4 版</span><span class="sxs-lookup"><span data-stu-id="8f2b4-161">Standard ECMA-334 4th Edition</span></span>|
|<span data-ttu-id="8f2b4-162">C# 3.0</span><span class="sxs-lookup"><span data-stu-id="8f2b4-162">C# 3.0</span></span>|[<span data-ttu-id="8f2b4-163">下载 DOC</span><span class="sxs-lookup"><span data-stu-id="8f2b4-163">Download DOC</span></span>](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc)|<span data-ttu-id="8f2b4-164">C# 语言规范版本 3.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="8f2b4-164">C# Language Specification Version 3.0: Microsoft Corporation</span></span>|
|<span data-ttu-id="8f2b4-165">C# 5.0</span><span class="sxs-lookup"><span data-stu-id="8f2b4-165">C# 5.0</span></span>|[<span data-ttu-id="8f2b4-166">下载 PDF</span><span class="sxs-lookup"><span data-stu-id="8f2b4-166">Download PDF</span></span>](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf)|<span data-ttu-id="8f2b4-167">标准 ECMA-334 第 5 版</span><span class="sxs-lookup"><span data-stu-id="8f2b4-167">Standard ECMA-334 5th Edition</span></span>|
|<span data-ttu-id="8f2b4-168">C# 6.0</span><span class="sxs-lookup"><span data-stu-id="8f2b4-168">C# 6.0</span></span>|[<span data-ttu-id="8f2b4-169">链接</span><span class="sxs-lookup"><span data-stu-id="8f2b4-169">Link</span></span>](../language-specification/index.md)|<span data-ttu-id="8f2b4-170">C# 语言规范版本 6 - 非官方草稿：.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="8f2b4-170">C# Language Specification Version 6 - Unofficial Draft: .NET Foundation</span></span>|
|<span data-ttu-id="8f2b4-171">C# 7.0 和更高版本</span><span class="sxs-lookup"><span data-stu-id="8f2b4-171">C# 7.0 and later</span></span>||<span data-ttu-id="8f2b4-172">当前不可用</span><span class="sxs-lookup"><span data-stu-id="8f2b4-172">not currently available</span></span>|

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="8f2b4-173">支持所有语言功能所需的最低编译器版本</span><span class="sxs-lookup"><span data-stu-id="8f2b4-173">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="8f2b4-174">[↩](#TISO1)<a name="FISO1">ISO1</a>：Microsoft Visual Studio/生成工具 .Net 2002 或捆绑的 .Net Framework 1.0 编译器</span><span class="sxs-lookup"><span data-stu-id="8f2b4-174">[↩](#TISO1)<a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="8f2b4-175">[↩](#TISO2)<a name="FISO2">ISO2</a>：Microsoft Visual Studio/生成工具 2005 或捆绑的 .Net Framework 2.0 编译器</span><span class="sxs-lookup"><span data-stu-id="8f2b4-175">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="8f2b4-176">[↩](#TCS3)<a name="FCS3">CS3</a>：Microsoft Visual Studio/生成工具 2008 或捆绑的 .Net Framework 3.5 编译器</span><span class="sxs-lookup"><span data-stu-id="8f2b4-176">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="8f2b4-177">[↩](#TCS4)<a name="FCS4">CS4</a>：Microsoft Visual Studio/生成工具 2010 或捆绑的 .Net Framework 4.0 编译器</span><span class="sxs-lookup"><span data-stu-id="8f2b4-177">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="8f2b4-178">[↩](#TCS5)<a name="FCS5">CS5</a>：Microsoft Visual Studio/生成工具 2012 或捆绑的 .Net Framework 4.5 编译器</span><span class="sxs-lookup"><span data-stu-id="8f2b4-178">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="8f2b4-179">[↩](#TCS6)<a name="FCS6">CS6</a>：Microsoft Visual Studio/生成工具 2015</span><span class="sxs-lookup"><span data-stu-id="8f2b4-179">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="8f2b4-180">[↩](#TCS7)<a name="FCS7">CS7</a>：Microsoft Visual Studio/生成工具 2017</span><span class="sxs-lookup"><span data-stu-id="8f2b4-180">[↩](#TCS7)<a name="FCS7">CS7</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   
<span data-ttu-id="8f2b4-181">[↩](#TCS71)<a name="FCS71">CS71</a>：Microsoft Visual Studio/生成工具 2017，版本 15.3</span><span class="sxs-lookup"><span data-stu-id="8f2b4-181">[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 2017, version 15.3</span></span>    
<span data-ttu-id="8f2b4-182">[↩](#TCS72)<a name="FCS72">CS72</a>：Microsoft Visual Studio/生成工具 2017，版本 15.5</span><span class="sxs-lookup"><span data-stu-id="8f2b4-182">[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 2017, version 15.5</span></span>    
<span data-ttu-id="8f2b4-183">[↩](#TCS73)<a name="FCS73">CS73</a>：Microsoft Visual Studio/生成工具 2017，版本 15.7</span><span class="sxs-lookup"><span data-stu-id="8f2b4-183">[↩](#TCS73)<a name="FCS73">CS73</a>: Microsoft Visual Studio/Build Tools 2017, version 15.7</span></span>    

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS8)<a name="FCS8">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
