---
title: -langversion（C# 编译器选项）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /langversion
helpviewer_keywords:
- /langversion compiler option [C#]
- -langversion compiler option [C#]
- langversion compiler option [C#]
ms.assetid: 3fb00b05-a0ff-4782-b313-13a4c0f62d94
caps.latest.revision: 33
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f1088221a96d0176f08b4c01044e20ab6238fc13
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2018
---
# <a name="-langversion-c-compiler-options"></a><span data-ttu-id="0b631-102">-langversion（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="0b631-102">-langversion (C# Compiler Options)</span></span>
<span data-ttu-id="0b631-103">使编译器仅接受包含在所选 C# 语言规范中的语法。</span><span class="sxs-lookup"><span data-stu-id="0b631-103">Causes the compiler to accept only syntax that is included in the chosen C# language specification.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b631-104">语法</span><span class="sxs-lookup"><span data-stu-id="0b631-104">Syntax</span></span>  
  
```console  
-langversion:option  
```  
  
## <a name="arguments"></a><span data-ttu-id="0b631-105">自变量</span><span class="sxs-lookup"><span data-stu-id="0b631-105">Arguments</span></span>  
 `option`  
 <span data-ttu-id="0b631-106">以下为有效值：</span><span class="sxs-lookup"><span data-stu-id="0b631-106">The following values are valid:</span></span>  
  
|<span data-ttu-id="0b631-107">选项</span><span class="sxs-lookup"><span data-stu-id="0b631-107">Option</span></span>|<span data-ttu-id="0b631-108">含义</span><span class="sxs-lookup"><span data-stu-id="0b631-108">Meaning</span></span>|  
|------------|-------------|  
|<span data-ttu-id="0b631-109">default</span><span class="sxs-lookup"><span data-stu-id="0b631-109">default</span></span>|<span data-ttu-id="0b631-110">编译器接受它可支持的最新主版本中的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="0b631-110">The compiler accepts all valid language syntax from the latest major version that it can support.</span></span> <span data-ttu-id="0b631-111"><sup id="TDefault">[默认](#FDefault)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-111"><sup id="TDefault">[Default](#FDefault)</sup></span></span>| 
|<span data-ttu-id="0b631-112">ISO-1</span><span class="sxs-lookup"><span data-stu-id="0b631-112">ISO-1</span></span>|<span data-ttu-id="0b631-113">编译器只接受 ISO/IEC 23270:2003 C# (1.0/1.1) 中所含的语法 <sup id="TISO1">[ISO1](#FISO1)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-113">The compiler accepts only syntax that is included in ISO/IEC 23270:2003 C# (1.0/1.1) <sup id="TISO1">[ISO1](#FISO1)</sup></span></span>|  
|<span data-ttu-id="0b631-114">ISO-2</span><span class="sxs-lookup"><span data-stu-id="0b631-114">ISO-2</span></span>|<span data-ttu-id="0b631-115">编译器只接受 ISO/IEC 23270:2006 C# (2.0) 中所含的语法 <sup id="TISO2">[ISO2](#FISO2)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-115">The compiler accepts only syntax that is included in ISO/IEC 23270:2006 C# (2.0) <sup id="TISO2">[ISO2](#FISO2)</sup></span></span>|
|<span data-ttu-id="0b631-116">3</span><span class="sxs-lookup"><span data-stu-id="0b631-116">3</span></span>|<span data-ttu-id="0b631-117">编译器只接受 C# 3.0 或更低版本中所含的语法 <sup id="TCS3">[CS3](#FCS3)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-117">The compiler accepts only syntax that is included in C# 3.0 or lower <sup id="TCS3">[CS3](#FCS3)</sup></span></span>|
|<span data-ttu-id="0b631-118">4</span><span class="sxs-lookup"><span data-stu-id="0b631-118">4</span></span>|<span data-ttu-id="0b631-119">编译器只接受 C# 4.0 或更低版本中所含的语法 <sup id="TCS4">[CS4](#FCS4)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-119">The compiler accepts only syntax that is included in C# 4.0 or lower <sup id="TCS4">[CS4](#FCS4)</sup></span></span>|
|<span data-ttu-id="0b631-120">5</span><span class="sxs-lookup"><span data-stu-id="0b631-120">5</span></span>|<span data-ttu-id="0b631-121">编译器只接受 C# 5.0 或更低版本中所含的语法 <sup id="TCS5">[CS5](#FCS5)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-121">The compiler accepts only syntax that is included in C# 5.0 or lower <sup id="TCS5">[CS5](#FCS5)</sup></span></span>|
|<span data-ttu-id="0b631-122">6</span><span class="sxs-lookup"><span data-stu-id="0b631-122">6</span></span>|<span data-ttu-id="0b631-123">编译器只接受 C# 6.0 或更低版本中所含的语法 <sup id="TCS6">[CS6](#FCS6)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-123">The compiler accepts only syntax that is included in C# 6.0 or lower <sup id="TCS6">[CS6](#FCS6)</sup></span></span>|
|<span data-ttu-id="0b631-124">7</span><span class="sxs-lookup"><span data-stu-id="0b631-124">7</span></span>|<span data-ttu-id="0b631-125">编译器只接受 C# 7.0 或更低版本中所含的语法 <sup id="TCS7">[CS7](#FCS7)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-125">The compiler accepts only syntax that is included in C# 7.0 or lower <sup id="TCS7">[CS7](#FCS7)</sup></span></span>|
|<span data-ttu-id="0b631-126">最新</span><span class="sxs-lookup"><span data-stu-id="0b631-126">latest</span></span>|<span data-ttu-id="0b631-127">编译器接受它可支持的所有有效语言语法。</span><span class="sxs-lookup"><span data-stu-id="0b631-127">The compiler accepts all valid language syntax that it can support.</span></span> <span data-ttu-id="0b631-128"><sup id="TLatest">[最新](#FLatest)</sup></span><span class="sxs-lookup"><span data-stu-id="0b631-128"><sup id="TLatest">[Latest](#FLatest)</sup></span></span>|
<!--- Uncomment and move these above
|latest| once they're officially released
|7.1|The compiler accepts only syntax that is included in C# 7.1 or lower <sup id="TCS71">[CS71](#FCS71)</sup>|
|7.2|The compiler accepts only syntax that is included in C# 7.2 or lower <sup id="TCS71">[CS72](#FCS72)</sup>|
|8|The compiler accepts only syntax that is included in C# 8 or lower <sup id="TCS71">[CS8](#FCS8)</sup>|
-->

  
## <a name="remarks"></a><span data-ttu-id="0b631-129">备注</span><span class="sxs-lookup"><span data-stu-id="0b631-129">Remarks</span></span>  
 <span data-ttu-id="0b631-130">C# 应用程序引用的元数据不受 -langversion 编译器选项约束。</span><span class="sxs-lookup"><span data-stu-id="0b631-130">Metadata referenced by your C# application is not subject to **-langversion** compiler option.</span></span>  
  
 <span data-ttu-id="0b631-131">每个版本的 C# 编译器都包含语言规范的扩展，因此 -langversion 不提供早期版本编译器的同等功能。</span><span class="sxs-lookup"><span data-stu-id="0b631-131">Because each version of the C# compiler contains extensions to the language specification, **-langversion** does not give you the equivalent functionality of an earlier version of the compiler.</span></span>  
 
 <span data-ttu-id="0b631-132">此外，虽然 C# 版本更新通常与主要的 .Net Framework 版本一致，但新的语法和功能不一定绑定到该特定的 Framework 版本。</span><span class="sxs-lookup"><span data-stu-id="0b631-132">Additionally, while C# version updates generally coincide with major .Net Framework releases, the new syntax and features are not necessarily tied to that specific framework version.</span></span> <span data-ttu-id="0b631-133">虽然新功能肯定会需要与 C# 修订版一起发布的新编译器更新，但每项具体功能都有自己的最小 .Net API 或公共语言运行时要求，这些要求通过包括 NuGet 包或其他库允许功能本身在下层框架上运行。</span><span class="sxs-lookup"><span data-stu-id="0b631-133">While the new features will definitely require a new compiler update that is also released alongside the C# revision, each specific feature has its own minimum .Net API or common language runtime requirements that may allow it to run on downlevel frameworks by including NuGet packages or other libraries.</span></span>
  
 <span data-ttu-id="0b631-134">无论使用哪一项 -langversion 设置，都将使用当前版本的公共语言运行时来创建 .exe 或 .dll。</span><span class="sxs-lookup"><span data-stu-id="0b631-134">Regardless of which **-langversion** setting you use, you will use the current version of the common language runtime to create your .exe or .dll.</span></span> <span data-ttu-id="0b631-135">友元程序集和 [-moduleassemblyname（C# 编译器选项）](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md)是一个例外，它们在 -langversion:ISO-1 下工作。</span><span class="sxs-lookup"><span data-stu-id="0b631-135">One exception is friend assemblies and [-moduleassemblyname (C# Compiler Option)](../../../csharp/language-reference/compiler-options/moduleassemblyname-compiler-option.md), which work under **-langversion:ISO-1**.</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="0b631-136">在 Visual Studio 开发环境中设置此编译器选项</span><span class="sxs-lookup"><span data-stu-id="0b631-136">To set this compiler option in the Visual Studio development environment</span></span>  
  
1.  <span data-ttu-id="0b631-137">打开项目的“属性”页。</span><span class="sxs-lookup"><span data-stu-id="0b631-137">Open the project's **Properties** page.</span></span>  
  
2.  <span data-ttu-id="0b631-138">单击“生成”属性页。</span><span class="sxs-lookup"><span data-stu-id="0b631-138">Click the **Build** property page.</span></span>  
  
3.  <span data-ttu-id="0b631-139">单击“高级”按钮。</span><span class="sxs-lookup"><span data-stu-id="0b631-139">Click the **Advanced** button.</span></span>  
  
4.  <span data-ttu-id="0b631-140">修改“语言版本”属性。</span><span class="sxs-lookup"><span data-stu-id="0b631-140">Modify the **Language Version** property.</span></span>  
  
 <span data-ttu-id="0b631-141">有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>。</span><span class="sxs-lookup"><span data-stu-id="0b631-141">For information about how to set this compiler option programmatically, see <xref:VSLangProj80.CSharpProjectConfigurationProperties3.LanguageVersion%2A>.</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="0b631-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b631-142">See Also</span></span>  
 [<span data-ttu-id="0b631-143">C# 编译器选项</span><span class="sxs-lookup"><span data-stu-id="0b631-143">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="0b631-144">管理项目和解决方案属性</span><span class="sxs-lookup"><span data-stu-id="0b631-144">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 
### <a name="c-language-specification"></a><span data-ttu-id="0b631-145">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="0b631-145">C# Language Specification</span></span>
 <span data-ttu-id="0b631-146">[C# 语言规范参考](../../../csharp/language-reference/language-specification/index.md)：.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="0b631-146">[C# Language Specification Reference](../../../csharp/language-reference/language-specification/index.md) : .NET Foundation</span></span>  
 <span data-ttu-id="0b631-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) 信息技术 - C# 语言规范：ISO 目录</span><span class="sxs-lookup"><span data-stu-id="0b631-147">C# 1.0/1.1 [ISO/IEC 23270:2003](https://www.iso.org/standard/36768.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="0b631-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) 信息技术 - C# 语言规范：ISO 目录</span><span class="sxs-lookup"><span data-stu-id="0b631-148">C# 2.0 [ISO/IEC 23270:2006](https://www.iso.org/standard/42926.html) Information technology -- C# Language Specification : ISO Catalogue</span></span>  
 <span data-ttu-id="0b631-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006（PDF 格式）：可免费获取的 ISO 标准</span><span class="sxs-lookup"><span data-stu-id="0b631-149">C# 2.0 [c042926_ISO_IEC_23270_2006(E).zip](http://standards.iso.org/ittf/PubliclyAvailableStandards/c042926_ISO_IEC_23270_2006(E).zip) ISO/IEC 23270:2006 in PDF format : ISO Freely Available Standards</span></span>  
 <span data-ttu-id="0b631-150">C# 3.0 [CSharp 语言规范.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# 语言规范版本 3.0：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0b631-150">C# 3.0 [CSharp Language Specification.doc](http://download.microsoft.com/download/3/8/8/388e7205-bc10-4226-b2a8-75351c669b09/CSharp%20Language%20Specification.doc) C# Language Specification Version 3.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="0b631-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) 标准 ECMA-334 第四版</span><span class="sxs-lookup"><span data-stu-id="0b631-151">C# 4.0 [Ecma-334.pdf](https://www.ecma-international.org/publications/files/ECMA-ST/Ecma-334.pdf) Standard ECMA-334 4th Edition</span></span>    
 <span data-ttu-id="0b631-152">C# 5.0 [CSharp 语言规范.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# 语言规范 5.0 版：Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="0b631-152">C# 5.0 [CSharp Language Specification.docx](https://www.microsoft.com/download/details.aspx?id=7029) C# Language Specification Version 5.0 : Microsoft Corporation</span></span>  
 <span data-ttu-id="0b631-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# 语言规范版本 6 - 非官方草稿：.NET Foundation</span><span class="sxs-lookup"><span data-stu-id="0b631-153">C# 6.0 [README.md](https://github.com/dotnet/csharplang/blob/master/spec/README.md) C# Language Specification Version 6 - Unofficial Draft : .NET Foundation</span></span>  
 <span data-ttu-id="0b631-154">C# 7.0（当前不可用）</span><span class="sxs-lookup"><span data-stu-id="0b631-154">C# 7.0 (not currently available)</span></span>  

<!--- Uncomment and add to the above when they become officially released
 C# 7.1 (spec is not yet finished)  
 C# 7.2 (spec is not yet finished)  
 C# 8.0 (spec is not yet finished)  
-->

### <a name="minimum-compiler-version-needed-to-support-all-language-features"></a><span data-ttu-id="0b631-155">支持所有语言功能所需的最低编译器版本</span><span class="sxs-lookup"><span data-stu-id="0b631-155">Minimum compiler version needed to support all language features</span></span>   
<span data-ttu-id="0b631-156">[↩](#TDefault)<a name="FDefault">默认</a><a name="FISO1">ISO1</a>：Microsoft Visual Studio/生成工具 .Net 2002 或捆绑的 .Net Framework 1.0 编译器</span><span class="sxs-lookup"><span data-stu-id="0b631-156">[↩](#TDefault)<a name="FDefault">Default</a>, <a name="FISO1">ISO1</a>: Microsoft Visual Studio/Build Tools .Net 2002 or bundled .Net Framework 1.0 compiler</span></span>     
<span data-ttu-id="0b631-157">[↩](#TISO2)<a name="FISO2">ISO2</a>：Microsoft Visual Studio/生成工具 2005 或捆绑的 .Net Framework 2.0 编译器</span><span class="sxs-lookup"><span data-stu-id="0b631-157">[↩](#TISO2)<a name="FISO2">ISO2</a>: Microsoft Visual Studio/Build Tools 2005 or bundled .Net Framework 2.0 compiler</span></span>    
<span data-ttu-id="0b631-158">[↩](#TCS3)<a name="FCS3">CS3</a>：Microsoft Visual Studio/生成工具 2008 或捆绑的 .Net Framework 3.5 编译器</span><span class="sxs-lookup"><span data-stu-id="0b631-158">[↩](#TCS3)<a name="FCS3">CS3</a>: Microsoft Visual Studio/Build Tools 2008 or bundled .Net Framework 3.5 compiler</span></span>    
<span data-ttu-id="0b631-159">[↩](#TCS4)<a name="FCS4">CS4</a>：Microsoft Visual Studio/生成工具 2010 或捆绑的 .Net Framework 4.0 编译器</span><span class="sxs-lookup"><span data-stu-id="0b631-159">[↩](#TCS4)<a name="FCS4">CS4</a>: Microsoft Visual Studio/Build Tools 2010 or bundled .Net Framework 4.0 compiler</span></span>    
<span data-ttu-id="0b631-160">[↩](#TCS5)<a name="FCS5">CS5</a>：Microsoft Visual Studio/生成工具 2012 或捆绑的 .Net Framework 4.5 编译器</span><span class="sxs-lookup"><span data-stu-id="0b631-160">[↩](#TCS5)<a name="FCS5">CS5</a>: Microsoft Visual Studio/Build Tools 2012 or bundled .Net Framework 4.5 compiler</span></span>    
<span data-ttu-id="0b631-161">[↩](#TCS6)<a name="FCS6">CS6</a>：Microsoft Visual Studio/生成工具 2015</span><span class="sxs-lookup"><span data-stu-id="0b631-161">[↩](#TCS6)<a name="FCS6">CS6</a>: Microsoft Visual Studio/Build Tools 2015</span></span>    
<span data-ttu-id="0b631-162">[↩](#TCS7)<a name="FCS7">CS7</a><a name="FLatest">最新</a>：Microsoft Visual Studio/生成工具 2017</span><span class="sxs-lookup"><span data-stu-id="0b631-162">[↩](#TCS7)<a name="FCS7">CS7</a>, <a name="FLatest">Latest</a>: Microsoft Visual Studio/Build Tools 2017</span></span>   

<!--- Uncomment and add to the above when they become officially released
[↩](#TCS71)<a name="FCS71">CS71</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS72)<a name="FCS72">CS72</a>: Microsoft Visual Studio/Build Tools 20??    
[↩](#TCS8)<a name="FCS71">CS8</a>: Microsoft Visual Studio/Build Tools 20??    
-->
