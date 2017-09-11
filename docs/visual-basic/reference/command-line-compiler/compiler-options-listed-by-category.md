---
title: "按类别列出的 Visual Basic 编译器选项 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, options
ms.assetid: fbe36f7a-7cfa-4f77-a8d4-2be5958568e3
caps.latest.revision: 24
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ae85d1ac5cf2bff05df25cf0cfc623f6266063b4
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="visual-basic-compiler-options-listed-by-category"></a><span data-ttu-id="ed7b1-102">按类别列出的 Visual Basic 编译器选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-102">Visual Basic Compiler Options Listed by Category</span></span>
<span data-ttu-id="ed7b1-103">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 命令行编译器用作一种编译来自 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 集成开发环境 (IDE) 的程序的替代方法提供。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-103">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler is provided as an alternative to compiling programs from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] integrated development environment (IDE).</span></span> <span data-ttu-id="ed7b1-104">以下是按功能分类排序的 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 命令行编译器选项的列表。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-104">The following is a list of the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] command-line compiler options sorted by functional category.</span></span>  
  
## <a name="compiler-output"></a><span data-ttu-id="ed7b1-105">编译器输出</span><span class="sxs-lookup"><span data-stu-id="ed7b1-105">Compiler Output</span></span>  
  
|<span data-ttu-id="ed7b1-106">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-106">Option</span></span>|<span data-ttu-id="ed7b1-107">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-107">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-108">/nologo</span><span class="sxs-lookup"><span data-stu-id="ed7b1-108">/nologo</span></span>](../../../visual-basic/reference/command-line-compiler/nologo.md)|<span data-ttu-id="ed7b1-109">禁止显示编译器横幅信息。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-109">Suppresses compiler banner information.</span></span>|  
|[<span data-ttu-id="ed7b1-110">/utf8output</span><span class="sxs-lookup"><span data-stu-id="ed7b1-110">/utf8output</span></span>](../../../visual-basic/reference/command-line-compiler/utf8output.md)|<span data-ttu-id="ed7b1-111">显示使用 UTF-8 编码的编译器输出。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-111">Displays compiler output using UTF-8 encoding.</span></span>|  
|[<span data-ttu-id="ed7b1-112">/verbose</span><span class="sxs-lookup"><span data-stu-id="ed7b1-112">/verbose</span></span>](../../../visual-basic/reference/command-line-compiler/verbose.md)|<span data-ttu-id="ed7b1-113">在编译期间输出其他信息。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-113">Outputs extra information during compilation.</span></span>|  
|`/modulename:<string>`|<span data-ttu-id="ed7b1-114">指定源模块的名称</span><span class="sxs-lookup"><span data-stu-id="ed7b1-114">Specify the name of the source module</span></span>|  
|[<span data-ttu-id="ed7b1-115">/preferreduilang</span><span class="sxs-lookup"><span data-stu-id="ed7b1-115">/preferreduilang</span></span>](../../../csharp/language-reference/compiler-options/preferreduilang-compiler-option.md)|<span data-ttu-id="ed7b1-116">指定编译器输出的语言。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-116">Specify a language for compiler output.</span></span>|  
  
## <a name="optimization"></a><span data-ttu-id="ed7b1-117">优化</span><span class="sxs-lookup"><span data-stu-id="ed7b1-117">Optimization</span></span>  
  
|<span data-ttu-id="ed7b1-118">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-118">Option</span></span>|<span data-ttu-id="ed7b1-119">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-119">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-120">/filealign</span><span class="sxs-lookup"><span data-stu-id="ed7b1-120">/filealign</span></span>](../../../visual-basic/reference/command-line-compiler/filealign.md)|<span data-ttu-id="ed7b1-121">指定输出文件各节的对齐位置。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-121">Specifies where to align the sections of the output file.</span></span>|  
|[<span data-ttu-id="ed7b1-122">/optimize</span><span class="sxs-lookup"><span data-stu-id="ed7b1-122">/optimize</span></span>](../../../visual-basic/reference/command-line-compiler/optimize.md)|<span data-ttu-id="ed7b1-123">启用/禁用优化。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-123">Enables/disables optimizations.</span></span>|  
  
## <a name="output-files"></a><span data-ttu-id="ed7b1-124">输出文件</span><span class="sxs-lookup"><span data-stu-id="ed7b1-124">Output Files</span></span>  
  
|<span data-ttu-id="ed7b1-125">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-125">Option</span></span>|<span data-ttu-id="ed7b1-126">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-126">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-127">/doc</span><span class="sxs-lookup"><span data-stu-id="ed7b1-127">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)|<span data-ttu-id="ed7b1-128">处理 XML 文件的文档注释。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-128">Process documentation comments to an XML file.</span></span>|  
|[<span data-ttu-id="ed7b1-129">/netcf</span><span class="sxs-lookup"><span data-stu-id="ed7b1-129">/netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)|<span data-ttu-id="ed7b1-130">设置编译器从而以 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 为目标。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-130">Sets the compiler to target the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>|  
|[<span data-ttu-id="ed7b1-131">/out</span><span class="sxs-lookup"><span data-stu-id="ed7b1-131">/out</span></span>](../../../visual-basic/reference/command-line-compiler/out.md)|<span data-ttu-id="ed7b1-132">指定输出目录。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-132">Specifies an output file.</span></span>|  
|[<span data-ttu-id="ed7b1-133">/target</span><span class="sxs-lookup"><span data-stu-id="ed7b1-133">/target</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)|<span data-ttu-id="ed7b1-134">指定输出的格式。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-134">Specifies the format of the output.</span></span>|  
  
## <a name="net-assemblies"></a><span data-ttu-id="ed7b1-135">.NET 程序集</span><span class="sxs-lookup"><span data-stu-id="ed7b1-135">.NET Assemblies</span></span>  
  
|<span data-ttu-id="ed7b1-136">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-136">Option</span></span>|<span data-ttu-id="ed7b1-137">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-137">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-138">/addmodule</span><span class="sxs-lookup"><span data-stu-id="ed7b1-138">/addmodule</span></span>](../../../visual-basic/reference/command-line-compiler/addmodule.md)|<span data-ttu-id="ed7b1-139">使编译器让指定文件中的所有类型信息可供当前正在编译的项目使用。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-139">Causes the compiler to make all type information from the specified file(s) available to the project you are currently compiling.</span></span>|  
|[<span data-ttu-id="ed7b1-140">/delaysign</span><span class="sxs-lookup"><span data-stu-id="ed7b1-140">/delaysign</span></span>](../../../visual-basic/reference/command-line-compiler/delaysign.md)|<span data-ttu-id="ed7b1-141">指定程序集是完全签名的还是部分签名的。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-141">Specifies whether the assembly will be fully or partially signed.</span></span>|  
|[<span data-ttu-id="ed7b1-142">/imports</span><span class="sxs-lookup"><span data-stu-id="ed7b1-142">/imports</span></span>](../../../visual-basic/reference/command-line-compiler/imports.md)|<span data-ttu-id="ed7b1-143">从指定的程序集导入命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-143">Imports a namespace from a specified assembly.</span></span>|  
|[<span data-ttu-id="ed7b1-144">/keycontainer</span><span class="sxs-lookup"><span data-stu-id="ed7b1-144">/keycontainer</span></span>](../../../visual-basic/reference/command-line-compiler/keycontainer.md)|<span data-ttu-id="ed7b1-145">指定密钥对的密钥容器名称从而为程序集赋予强名称。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-145">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>|  
|[<span data-ttu-id="ed7b1-146">/keyfile</span><span class="sxs-lookup"><span data-stu-id="ed7b1-146">/keyfile</span></span>](../../../visual-basic/reference/command-line-compiler/keyfile.md)|<span data-ttu-id="ed7b1-147">指定包含密钥或密钥对的文件从而为程序集赋予强名称。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-147">Specifies a file containing a key or key pair to give an assembly a strong name.</span></span>|  
|[<span data-ttu-id="ed7b1-148">/libpath</span><span class="sxs-lookup"><span data-stu-id="ed7b1-148">/libpath</span></span>](../../../visual-basic/reference/command-line-compiler/libpath.md)|<span data-ttu-id="ed7b1-149">指定引用的程序集的位置[/引用](../../../visual-basic/reference/command-line-compiler/reference.md)选项。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-149">Specifies the location of assemblies referenced by the [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>|  
|[<span data-ttu-id="ed7b1-150">/reference</span><span class="sxs-lookup"><span data-stu-id="ed7b1-150">/reference</span></span>](../../../visual-basic/reference/command-line-compiler/reference.md)|<span data-ttu-id="ed7b1-151">从程序集导入元数据。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-151">Imports metadata from an assembly.</span></span>|  
|[<span data-ttu-id="ed7b1-152">/moduleassemblyname</span><span class="sxs-lookup"><span data-stu-id="ed7b1-152">/moduleassemblyname</span></span>](../../../visual-basic/reference/command-line-compiler/moduleassemblyname.md)|<span data-ttu-id="ed7b1-153">指定模块所属程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-153">Specifies the name of the assembly that a module will be a part of.</span></span>|  
|`/analyzer`|<span data-ttu-id="ed7b1-154">从此程序集（缩写形式：/a）运行分析器</span><span class="sxs-lookup"><span data-stu-id="ed7b1-154">Run the analyzers from this assembly (Short form: /a)</span></span>|  
|`/additionalfile`|<span data-ttu-id="ed7b1-155">命名其他文件，这些文件不会直接影响代码生成，但可能由分析器用于生成错误或警告。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-155">Names additional files that don't directly affect code generation but may be used by analyzers for producing errors or warnings.</span></span>|  
  
## <a name="debuggingerror-checking"></a><span data-ttu-id="ed7b1-156">调试/错误检查</span><span class="sxs-lookup"><span data-stu-id="ed7b1-156">Debugging/Error Checking</span></span>  
  
|<span data-ttu-id="ed7b1-157">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-157">Option</span></span>|<span data-ttu-id="ed7b1-158">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-158">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-159">/bugreport</span><span class="sxs-lookup"><span data-stu-id="ed7b1-159">/bugreport</span></span>](../../../visual-basic/reference/command-line-compiler/bugreport.md)|<span data-ttu-id="ed7b1-160">创建一个文件，其中包含可以轻松报告 bug 的信息。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-160">Creates a file that contains information that makes it easy to report a bug.</span></span>|  
|[<span data-ttu-id="ed7b1-161">/debug</span><span class="sxs-lookup"><span data-stu-id="ed7b1-161">/debug</span></span>](../../../visual-basic/reference/command-line-compiler/debug.md)|<span data-ttu-id="ed7b1-162">生成调试信息。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-162">Produces debugging information.</span></span>|  
|[<span data-ttu-id="ed7b1-163">/nowarn</span><span class="sxs-lookup"><span data-stu-id="ed7b1-163">/nowarn</span></span>](../../../visual-basic/reference/command-line-compiler/nowarn.md)|<span data-ttu-id="ed7b1-164">禁止编译器生成警告的能力。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-164">Suppresses the compiler's ability to generate warnings.</span></span>|  
|[<span data-ttu-id="ed7b1-165">/quiet</span><span class="sxs-lookup"><span data-stu-id="ed7b1-165">/quiet</span></span>](../../../visual-basic/reference/command-line-compiler/quiet.md)|<span data-ttu-id="ed7b1-166">阻止编译器显示与语法相关的错误和警告的代码。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-166">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>|  
|[<span data-ttu-id="ed7b1-167">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="ed7b1-167">/removeintchecks</span></span>](../../../visual-basic/reference/command-line-compiler/removeintchecks.md)|<span data-ttu-id="ed7b1-168">禁用整数溢出检查。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-168">Disables integer overflow checking.</span></span>|  
|[<span data-ttu-id="ed7b1-169">/warnaserror</span><span class="sxs-lookup"><span data-stu-id="ed7b1-169">/warnaserror</span></span>](../../../visual-basic/reference/command-line-compiler/warnaserror.md)|<span data-ttu-id="ed7b1-170">将警告提升为错误。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-170">Promotes warnings to errors.</span></span>|  
|`/ruleset:<file>`|<span data-ttu-id="ed7b1-171">指定可禁用特定诊断的规则集文件。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-171">Specify a ruleset file that disables specific diagnostics.</span></span>|  
  
## <a name="help"></a><span data-ttu-id="ed7b1-172">帮助</span><span class="sxs-lookup"><span data-stu-id="ed7b1-172">Help</span></span>  
  
|<span data-ttu-id="ed7b1-173">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-173">Option</span></span>|<span data-ttu-id="ed7b1-174">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-174">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-175">/?</span><span class="sxs-lookup"><span data-stu-id="ed7b1-175">/?</span></span>](../../../visual-basic/reference/command-line-compiler/help.md)|<span data-ttu-id="ed7b1-176">显示编译器选项。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-176">Displays the compiler options.</span></span> <span data-ttu-id="ed7b1-177">此命令等同于指定 `/help` 选项。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-177">This command is the same as specifying the `/help` option.</span></span> <span data-ttu-id="ed7b1-178">未进行编译。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-178">No compilation occurs.</span></span>|  
|[<span data-ttu-id="ed7b1-179">/help</span><span class="sxs-lookup"><span data-stu-id="ed7b1-179">/help</span></span>](../../../visual-basic/reference/command-line-compiler/help.md)|<span data-ttu-id="ed7b1-180">显示编译器选项。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-180">Displays the compiler options.</span></span> <span data-ttu-id="ed7b1-181">此命令等同于指定 `/?` 选项。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-181">This command is the same as specifying the `/?` option.</span></span> <span data-ttu-id="ed7b1-182">未进行编译。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-182">No compilation occurs.</span></span>|  
  
## <a name="language"></a><span data-ttu-id="ed7b1-183">语言</span><span class="sxs-lookup"><span data-stu-id="ed7b1-183">Language</span></span>  
  
|<span data-ttu-id="ed7b1-184">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-184">Option</span></span>|<span data-ttu-id="ed7b1-185">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-185">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-186">/langversion</span><span class="sxs-lookup"><span data-stu-id="ed7b1-186">/langversion</span></span>](../../../visual-basic/reference/command-line-compiler/langversion.md)|<span data-ttu-id="ed7b1-187">指定语言版本︰ 9 | 9.0 | 10 | 10.0 | 11 | 11.0。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-187">Specify language version: 9&#124;9.0&#124;10&#124;10.0&#124;11&#124;11.0.</span></span>|  
|[<span data-ttu-id="ed7b1-188">/optionexplicit</span><span class="sxs-lookup"><span data-stu-id="ed7b1-188">/optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)|<span data-ttu-id="ed7b1-189">强制执行显式声明变量。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-189">Enforces explicit declaration of variables.</span></span>|  
|[<span data-ttu-id="ed7b1-190">/optionstrict</span><span class="sxs-lookup"><span data-stu-id="ed7b1-190">/optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)|<span data-ttu-id="ed7b1-191">执行严格的类语义。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-191">Enforces strict type semantics.</span></span>|  
|[<span data-ttu-id="ed7b1-192">/optioncompare</span><span class="sxs-lookup"><span data-stu-id="ed7b1-192">/optioncompare</span></span>](../../../visual-basic/reference/command-line-compiler/optioncompare.md)|<span data-ttu-id="ed7b1-193">指定字符串比较是否应为二进制，或是否应使用特定于区域设置的文本语义。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-193">Specifies whether string comparisons should be binary or use locale-specific text semantics.</span></span>|  
|[<span data-ttu-id="ed7b1-194">/optioninfer</span><span class="sxs-lookup"><span data-stu-id="ed7b1-194">/optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)|<span data-ttu-id="ed7b1-195">允许在变量声明中使用局部类型推理。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-195">Enables the use of local type inference in variable declarations.</span></span>|  
  
## <a name="preprocessor"></a><span data-ttu-id="ed7b1-196">预处理器</span><span class="sxs-lookup"><span data-stu-id="ed7b1-196">Preprocessor</span></span>  
  
|<span data-ttu-id="ed7b1-197">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-197">Option</span></span>|<span data-ttu-id="ed7b1-198">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-198">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-199">/define</span><span class="sxs-lookup"><span data-stu-id="ed7b1-199">/define</span></span>](../../../visual-basic/reference/command-line-compiler/define.md)|<span data-ttu-id="ed7b1-200">定义条件编译的符号。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-200">Defines symbols for conditional compilation.</span></span>|  
  
## <a name="resources"></a><span data-ttu-id="ed7b1-201">资源</span><span class="sxs-lookup"><span data-stu-id="ed7b1-201">Resources</span></span>  
  
|<span data-ttu-id="ed7b1-202">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-202">Option</span></span>|<span data-ttu-id="ed7b1-203">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-203">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-204">/linkresource</span><span class="sxs-lookup"><span data-stu-id="ed7b1-204">/linkresource</span></span>](../../../visual-basic/reference/command-line-compiler/linkresource.md)|<span data-ttu-id="ed7b1-205">创建指向托管资源的链接。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-205">Creates a link to a managed resource.</span></span>|  
|[<span data-ttu-id="ed7b1-206">/resource</span><span class="sxs-lookup"><span data-stu-id="ed7b1-206">/resource</span></span>](../../../visual-basic/reference/command-line-compiler/resource.md)|<span data-ttu-id="ed7b1-207">将托管资源嵌入程序集。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-207">Embeds a managed resource in an assembly.</span></span>|  
|[<span data-ttu-id="ed7b1-208">/win32icon</span><span class="sxs-lookup"><span data-stu-id="ed7b1-208">/win32icon</span></span>](../../../visual-basic/reference/command-line-compiler/win32icon.md)|<span data-ttu-id="ed7b1-209">将 .ico 文件插入到输出文件。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-209">Inserts an .ico file into the output file.</span></span>|  
|[<span data-ttu-id="ed7b1-210">/win32resource</span><span class="sxs-lookup"><span data-stu-id="ed7b1-210">/win32resource</span></span>](../../../visual-basic/reference/command-line-compiler/win32resource.md)|<span data-ttu-id="ed7b1-211">将 Win32 资源插入到输出文件。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-211">Inserts a Win32 resource into the output file.</span></span>|  
  
## <a name="miscellaneous"></a><span data-ttu-id="ed7b1-212">杂项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-212">Miscellaneous</span></span>  
  
|<span data-ttu-id="ed7b1-213">选项</span><span class="sxs-lookup"><span data-stu-id="ed7b1-213">Option</span></span>|<span data-ttu-id="ed7b1-214">目标</span><span class="sxs-lookup"><span data-stu-id="ed7b1-214">Purpose</span></span>|  
|---|---|  
|[<span data-ttu-id="ed7b1-215">@（指定响应文件）</span><span class="sxs-lookup"><span data-stu-id="ed7b1-215">@ (Specify Response File)</span></span>](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)|<span data-ttu-id="ed7b1-216">指定响应文件。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-216">Specifies a response file.</span></span>|  
|[<span data-ttu-id="ed7b1-217">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="ed7b1-217">/baseaddress</span></span>](../../../visual-basic/reference/command-line-compiler/baseaddress.md)|<span data-ttu-id="ed7b1-218">指定的 DLL 的基址。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-218">Specifies the base address of a DLL.</span></span>|  
|[<span data-ttu-id="ed7b1-219">/codepage</span><span class="sxs-lookup"><span data-stu-id="ed7b1-219">/codepage</span></span>](../../../visual-basic/reference/command-line-compiler/codepage.md)|<span data-ttu-id="ed7b1-220">指定要用于编译中所有源代码文件的代码页。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-220">Specifies the code page to use for all source code files in the compilation.</span></span>|  
|[<span data-ttu-id="ed7b1-221">/errorreport</span><span class="sxs-lookup"><span data-stu-id="ed7b1-221">/errorreport</span></span>](../../../visual-basic/reference/command-line-compiler/errorreport.md)|<span data-ttu-id="ed7b1-222">指定 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 编译器应报告内部编译器错误的方式。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-222">Specifies how the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler should report internal compiler errors.</span></span>|  
|[<span data-ttu-id="ed7b1-223">/highentropyva</span><span class="sxs-lookup"><span data-stu-id="ed7b1-223">/highentropyva</span></span>](../../../visual-basic/reference/command-line-compiler/highentropyva.md)|<span data-ttu-id="ed7b1-224">向 Windows 内核提供下列信息：特定的可执行文件是否支持高熵地址空间布局随机化 (ASLR)。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-224">Tells the Windows kernel whether a particular executable supports high entropy Address Space Layout Randomization (ASLR).</span></span>|  
|[<span data-ttu-id="ed7b1-225">/main</span><span class="sxs-lookup"><span data-stu-id="ed7b1-225">/main</span></span>](../../../visual-basic/reference/command-line-compiler/main.md)|<span data-ttu-id="ed7b1-226">指定的类，包含`Sub``Main`启动时要使用的过程。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-226">Specifies the class that contains the `Sub``Main` procedure to use at startup.</span></span>|  
|[<span data-ttu-id="ed7b1-227">/noconfig</span><span class="sxs-lookup"><span data-stu-id="ed7b1-227">/noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)|<span data-ttu-id="ed7b1-228">不要使用 Vbc.rsp 进行编译</span><span class="sxs-lookup"><span data-stu-id="ed7b1-228">Do not compile with Vbc.rsp</span></span>|  
|[<span data-ttu-id="ed7b1-229">/nostdlib</span><span class="sxs-lookup"><span data-stu-id="ed7b1-229">/nostdlib</span></span>](../../../visual-basic/reference/command-line-compiler/nostdlib.md)|<span data-ttu-id="ed7b1-230">导致编译器不引用标准库。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-230">Causes the compiler not to reference the standard libraries.</span></span>|  
|[<span data-ttu-id="ed7b1-231">/nowin32manifest</span><span class="sxs-lookup"><span data-stu-id="ed7b1-231">/nowin32manifest</span></span>](../../../visual-basic/reference/command-line-compiler/nowin32manifest.md)|<span data-ttu-id="ed7b1-232">指示编译器不在可执行文件中嵌入任何应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-232">Instructs the compiler not to embed any application manifest into the executable file.</span></span>|  
|[<span data-ttu-id="ed7b1-233">/platform</span><span class="sxs-lookup"><span data-stu-id="ed7b1-233">/platform</span></span>](../../../visual-basic/reference/command-line-compiler/platform.md)|<span data-ttu-id="ed7b1-234">为输出文件指定编译器面向的处理器平台。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-234">Specifies the processor platform the compiler targets for the output file.</span></span>|  
|[<span data-ttu-id="ed7b1-235">/recurse</span><span class="sxs-lookup"><span data-stu-id="ed7b1-235">/recurse</span></span>](../../../visual-basic/reference/command-line-compiler/recurse.md)|<span data-ttu-id="ed7b1-236">搜索要编译的源文件的子目录。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-236">Searches subdirectories for source files to compile.</span></span>|  
|[<span data-ttu-id="ed7b1-237">/rootnamespace</span><span class="sxs-lookup"><span data-stu-id="ed7b1-237">/rootnamespace</span></span>](../../../visual-basic/reference/command-line-compiler/rootnamespace.md)|<span data-ttu-id="ed7b1-238">指定所有类型声明的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-238">Specifies a namespace for all type declarations.</span></span>|  
|[<span data-ttu-id="ed7b1-239">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="ed7b1-239">/sdkpath</span></span>](../../../visual-basic/reference/command-line-compiler/sdkpath.md)|<span data-ttu-id="ed7b1-240">指定 Mscorlib.dll 和 Microsoft.VisualBasic.dll 的位置。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-240">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>|  
|[<span data-ttu-id="ed7b1-241">/vbruntime</span><span class="sxs-lookup"><span data-stu-id="ed7b1-241">/vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)|<span data-ttu-id="ed7b1-242">指定编译器应在不引用 Visual Basic 运行库的情况下进行编译，或在引用特定运行库的情况下进行编译。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-242">Specifies that the compiler should compile without a reference to the Visual Basic Runtime Library, or with a reference to a specific runtime library.</span></span>|  
|[<span data-ttu-id="ed7b1-243">/win32manifest</span><span class="sxs-lookup"><span data-stu-id="ed7b1-243">/win32manifest</span></span>](../../../visual-basic/reference/command-line-compiler/win32manifest.md)|<span data-ttu-id="ed7b1-244">标识用户定义的 Win32 应用程序清单文件要嵌入到项目的可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-244">Identifies a user-defined Win32 application manifest file to be embedded into a project's portable executable (PE) file.</span></span>|  
|`/parallel[+&#124;-]`|<span data-ttu-id="ed7b1-245">指定是否使用并发生成 (+)。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-245">Specifies whether to use concurrent build (+).</span></span>|  
|`/checksumalgorithm:<alg>`|<span data-ttu-id="ed7b1-246">指定用于计算 PDB 中存储的源文件校验和的算法。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-246">Specify the algorithm for calculating the source file checksum stored in PDB.</span></span>  <span data-ttu-id="ed7b1-247">支持的值为：SHA1（默认值）或 SHA256。</span><span class="sxs-lookup"><span data-stu-id="ed7b1-247">Supported values are: SHA1 (default) or SHA256.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ed7b1-248">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed7b1-248">See Also</span></span>  
 <span data-ttu-id="ed7b1-249">[按字母顺序列出的 Visual Basic 编译器选项](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md) </span><span class="sxs-lookup"><span data-stu-id="ed7b1-249">[Visual Basic Compiler Options Listed Alphabetically](../../../visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically.md) </span></span>  
<span data-ttu-id="ed7b1-250"> [项目设计器简介](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7) </span><span class="sxs-lookup"><span data-stu-id="ed7b1-250"> [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7) </span></span>  
<span data-ttu-id="ed7b1-251"> [按字母顺序列出的 C# 编译器选项](../../../csharp/language-reference/compiler-options/listed-alphabetically.md) </span><span class="sxs-lookup"><span data-stu-id="ed7b1-251"> [C# Compiler Options Listed Alphabetically](../../../csharp/language-reference/compiler-options/listed-alphabetically.md) </span></span>  
<span data-ttu-id="ed7b1-252"> [按类别列出的 C# 编译器选项](../../../csharp/language-reference/compiler-options/listed-by-category.md)</span><span class="sxs-lookup"><span data-stu-id="ed7b1-252"> [C# Compiler Options Listed by Category](../../../csharp/language-reference/compiler-options/listed-by-category.md)</span></span>
