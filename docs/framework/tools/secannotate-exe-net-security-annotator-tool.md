---
title: "SecAnnotate.exe（.NET 安全批注器工具）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SecAnnotate.exe
- Security Annotator tool
ms.assetid: 8104d208-7813-4a1d-8a75-58f9a7bcb8c9
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f7051e753c324933828e2447752f9c5ea13ed9d7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="secannotateexe-net-security-annotator-tool"></a><span data-ttu-id="9e6e5-102">SecAnnotate.exe（.NET 安全批注器工具）</span><span class="sxs-lookup"><span data-stu-id="9e6e5-102">SecAnnotate.exe (.NET Security Annotator Tool)</span></span>
<span data-ttu-id="9e6e5-103">.NET 安全性批注器工具 (SecAnnotate.exe) 是标识一个或多个程序集的 `SecurityCritical` 和 `SecuritySafeCritical` 部分的命令行应用程序。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-103">The .NET Security Annotator tool (SecAnnotate.exe) is a command-line application that identifies the `SecurityCritical` and `SecuritySafeCritical` portions of one or more assemblies.</span></span>  
  
 <span data-ttu-id="9e6e5-104">[安全性批注器](http://go.microsoft.com/fwlink/?LinkId=198007)是一个 Visual Studio 扩展，提供了 SecAnnotate.exe 的图形用户界面，使用户能够从 Visual Studio 中运行该工具。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-104">A Visual Studio extension, [Security Annotator](http://go.microsoft.com/fwlink/?LinkId=198007), provides a graphical user interface to SecAnnotate.exe and enables you to run the tool from Visual Studio.</span></span>  
  
 <span data-ttu-id="9e6e5-105">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="9e6e5-106">若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-106">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="9e6e5-107">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-107">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="9e6e5-108">在命令提示符处，键入以下内容，其中，parameters 将在下一部分进行介绍，assemblies 由一个或多个由空格分隔的程序集名称组成：</span><span class="sxs-lookup"><span data-stu-id="9e6e5-108">At the command prompt, type the following, where *parameters* are described in the following section, and *assemblies* consist of one or more assembly names separated by blanks:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e6e5-109">语法</span><span class="sxs-lookup"><span data-stu-id="9e6e5-109">Syntax</span></span>  
  
```  
SecAnnotate.exe [parameters] [assemblies]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9e6e5-110">参数</span><span class="sxs-lookup"><span data-stu-id="9e6e5-110">Parameters</span></span>  
  
|<span data-ttu-id="9e6e5-111">选项</span><span class="sxs-lookup"><span data-stu-id="9e6e5-111">Option</span></span>|<span data-ttu-id="9e6e5-112">描述</span><span class="sxs-lookup"><span data-stu-id="9e6e5-112">Description</span></span>|  
|------------|-----------------|  
|`/a`<br /><br /> <span data-ttu-id="9e6e5-113">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-113">or</span></span><br /><br /> `/showstatistics`|<span data-ttu-id="9e6e5-114">显示与正在分析的程序集中的透明度使用有关的统计信息。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-114">Shows statistics about the use of transparency in assemblies that are being analyzed.</span></span>|  
|<span data-ttu-id="9e6e5-115">`/d:` directory</span><span class="sxs-lookup"><span data-stu-id="9e6e5-115">`/d:` *directory*</span></span><br /><br /> <span data-ttu-id="9e6e5-116">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-116">or</span></span><br /><br /> <span data-ttu-id="9e6e5-117">`/referencedir:` directory</span><span class="sxs-lookup"><span data-stu-id="9e6e5-117">`/referencedir:` *directory*</span></span>|<span data-ttu-id="9e6e5-118">指定在批注过程中搜索依赖程序集的目录。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-118">Specifies a directory to search for dependent assemblies during annotation.</span></span>|  
|`/i`<br /><br /> <span data-ttu-id="9e6e5-119">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-119">or</span></span><br /><br /> `/includesignatures`|<span data-ttu-id="9e6e5-120">包括批注报告文件中的扩展签名信息。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-120">Includes extended signature information in the annotation report file.</span></span>|  
|`/n`<br /><br /> <span data-ttu-id="9e6e5-121">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-121">or</span></span><br /><br /> `/nogac`|<span data-ttu-id="9e6e5-122">禁止搜索全局程序集缓存中引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-122">Suppresses searching for referenced assemblies in the global assembly cache.</span></span>|  
|<span data-ttu-id="9e6e5-123">`/o:` output.xml</span><span class="sxs-lookup"><span data-stu-id="9e6e5-123">`/o:` *output.xml*</span></span><br /><br /> <span data-ttu-id="9e6e5-124">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-124">or</span></span><br /><br /> <span data-ttu-id="9e6e5-125">`/out:` output.xml</span><span class="sxs-lookup"><span data-stu-id="9e6e5-125">`/out:` *output.xml*</span></span>|<span data-ttu-id="9e6e5-126">指定输出批注文件。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-126">Specifies the output annotation file.</span></span>|  
|<span data-ttu-id="9e6e5-127">`/p:` maxpasses</span><span class="sxs-lookup"><span data-stu-id="9e6e5-127">`/p:` *maxpasses*</span></span><br /><br /> <span data-ttu-id="9e6e5-128">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-128">or</span></span><br /><br /> <span data-ttu-id="9e6e5-129">`/maximumpasses:` maxpasses</span><span class="sxs-lookup"><span data-stu-id="9e6e5-129">`/maximumpasses:` *maxpasses*</span></span>|<span data-ttu-id="9e6e5-130">指定停止生成新的批注前要对程序集进行的最大批注轮数。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-130">Specifies the maximum number of annotation passes to make on assemblies before stopping the generation of new annotations.</span></span>|  
|`/q`<br /><br /> <span data-ttu-id="9e6e5-131">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-131">or</span></span><br /><br /> `/quiet`|<span data-ttu-id="9e6e5-132">指定安静模式，在此模式下，批注器不会输出状态消息；它只会输出错误信息。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-132">Specifies quiet mode, in which the annotator does not output status messages; it outputs only error information.</span></span>|  
|<span data-ttu-id="9e6e5-133">`/r:` *assembly*</span><span class="sxs-lookup"><span data-stu-id="9e6e5-133">`/r:` *assembly*</span></span><br /><br /> <span data-ttu-id="9e6e5-134">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-134">or</span></span><br /><br /> <span data-ttu-id="9e6e5-135">`/referenceassembly:` *assembly*</span><span class="sxs-lookup"><span data-stu-id="9e6e5-135">`/referenceassembly:` *assembly*</span></span>|<span data-ttu-id="9e6e5-136">当在批注过程中解析依赖程序集时，包含指定的程序集。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-136">Includes the specified assembly when resolving dependent assemblies during annotation.</span></span> <span data-ttu-id="9e6e5-137">引用程序集获得的优先级高于在引用路径中找到的程序集。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-137">Reference assemblies are given priority over assemblies that are found in the reference path.</span></span>|  
|<span data-ttu-id="9e6e5-138">`/s:` rulename</span><span class="sxs-lookup"><span data-stu-id="9e6e5-138">`/s:` *rulename*</span></span><br /><br /> <span data-ttu-id="9e6e5-139">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-139">or</span></span><br /><br /> <span data-ttu-id="9e6e5-140">`/suppressrule:` rulename</span><span class="sxs-lookup"><span data-stu-id="9e6e5-140">`/suppressrule:` *rulename*</span></span>|<span data-ttu-id="9e6e5-141">禁止对输入程序集运行指定的透明度规则。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-141">Suppresses running the specified transparency rule on the input assemblies.</span></span>|  
|`/t`<br /><br /> <span data-ttu-id="9e6e5-142">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-142">or</span></span><br /><br /> `/forcetransparent`|<span data-ttu-id="9e6e5-143">强制批准器工具将所有没有任何透明度批注的程序集作为完全透明来处理。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-143">Forces the Annotator tool to treat all assemblies that do not have any transparency annotations as if they were entirely transparent.</span></span>|  
|<span data-ttu-id="9e6e5-144">`/t`:assembly</span><span class="sxs-lookup"><span data-stu-id="9e6e5-144">`/t`:*assembly*</span></span><br /><br /> <span data-ttu-id="9e6e5-145">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-145">or</span></span><br /><br /> <span data-ttu-id="9e6e5-146">`/forcetransparent`:assembly</span><span class="sxs-lookup"><span data-stu-id="9e6e5-146">`/forcetransparent`:*assembly*</span></span>|<span data-ttu-id="9e6e5-147">将给定程序集强制为透明，而无论其当前程序集级别批注如何。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-147">Force the given assembly to be transparent, regardless of its current assembly-level annotations.</span></span>|  
|||  
|`/v`<br /><br /> <span data-ttu-id="9e6e5-148">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-148">or</span></span><br /><br /> `/verify`|<span data-ttu-id="9e6e5-149">仅验证程序集的批注是否正确；不会尝试进行多轮验证来查找所有需要的批注（前提是程序集不会验证）。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-149">Verifies only that an assembly's annotations are correct; does not attempt to make multiple passes to find all required annotations if the assembly does not verify.</span></span>|  
|`/x`<br /><br /> <span data-ttu-id="9e6e5-150">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-150">or</span></span><br /><br /> `/verbose`|<span data-ttu-id="9e6e5-151">指定批注时的详细输出。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-151">Specifies verbose output while annotating.</span></span>|  
|<span data-ttu-id="9e6e5-152">`/y:` directory</span><span class="sxs-lookup"><span data-stu-id="9e6e5-152">`/y:` *directory*</span></span><br /><br /> <span data-ttu-id="9e6e5-153">或</span><span class="sxs-lookup"><span data-stu-id="9e6e5-153">or</span></span><br /><br /> <span data-ttu-id="9e6e5-154">`/symbolpath:` directory</span><span class="sxs-lookup"><span data-stu-id="9e6e5-154">`/symbolpath:` *directory*</span></span>|<span data-ttu-id="9e6e5-155">当在批注过程中搜索符号文件时，包含指定的目录。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-155">Includes the specified directory when searching for symbol files during annotation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e6e5-156">备注</span><span class="sxs-lookup"><span data-stu-id="9e6e5-156">Remarks</span></span>  
 <span data-ttu-id="9e6e5-157">参数和程序集也可能在命令行上指定的响应文件中提供，且带有前缀 at 符号 (@)。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-157">Parameters and assemblies may also be provided in a response file that is specified on the command line and prefixed with an at sign (@).</span></span> <span data-ttu-id="9e6e5-158">响应文件中的每行应包含单个参数或程序集名称。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-158">Each line in the response file should contain a single parameter or assembly name.</span></span>  
  
 <span data-ttu-id="9e6e5-159">有关 .NET 安全性批注器的详细信息，请参阅 .NET 安全性博客中的[使用 SecAnnotate 分析程序集中的透明度冲突](http://go.microsoft.com/fwlink/?LinkId=187648)。</span><span class="sxs-lookup"><span data-stu-id="9e6e5-159">For more information about the .NET Security Annotator, see the entry [Using SecAnnotate to Analyze Your Assemblies for Transparency Violations](http://go.microsoft.com/fwlink/?LinkId=187648) in the .NET Security blog.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9e6e5-160">示例</span><span class="sxs-lookup"><span data-stu-id="9e6e5-160">Examples</span></span>
