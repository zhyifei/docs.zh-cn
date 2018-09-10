---
title: Peverify.exe（PEVerify 工具）
ms.date: 03/30/2017
helpviewer_keywords:
- portable executable files, PEVerify
- verifying MSIL and metadata
- PEVerify tool
- type safety requirements
- MSIL
- PEverify.exe
- PE files, PEVerify
ms.assetid: f4f46f9e-8d08-4e66-a94b-0c69c9b0bbfa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ae36736ac7174ff7f77ae5bba45e1fd3880169c
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44197617"
---
# <a name="peverifyexe-peverify-tool"></a><span data-ttu-id="96ffd-102">Peverify.exe（PEVerify 工具）</span><span class="sxs-lookup"><span data-stu-id="96ffd-102">Peverify.exe (PEVerify Tool)</span></span>
<span data-ttu-id="96ffd-103">PEVerify 工具有助于生成 Microsoft 中间语言 (MSIL) 的开发人员（如编译器编写者、脚本引擎开发人员等）确定其 MSIL 代码及关联的元数据是否满足类型安全要求。</span><span class="sxs-lookup"><span data-stu-id="96ffd-103">The PEVerify tool helps developers who generate Microsoft intermediate language (MSIL) (such as compiler writers, script engine developers, and so on) to determine whether their MSIL code and associated metadata meet type safety requirements.</span></span> <span data-ttu-id="96ffd-104">某些编译器仅当你避免使用某些语言构造时才生成可验证的类型安全代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-104">Some compilers generate verifiably type-safe code only if you avoid using certain language constructs.</span></span> <span data-ttu-id="96ffd-105">如果你作为开发人员正在使用此类编译器，则可能需要确认你未危害代码的类型安全性。</span><span class="sxs-lookup"><span data-stu-id="96ffd-105">If, as a developer, you are using such a compiler, you may want to verify that you have not compromised the type safety of your code.</span></span> <span data-ttu-id="96ffd-106">在这种情况下，你可以对文件运行 PEVerify 工具来检查 MSIL 和元数据。</span><span class="sxs-lookup"><span data-stu-id="96ffd-106">In this situation, you can run the PEVerify tool on your files to check the MSIL and metadata.</span></span>  
  
 <span data-ttu-id="96ffd-107">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="96ffd-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="96ffd-108">若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="96ffd-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="96ffd-109">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="96ffd-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="96ffd-110">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="96ffd-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96ffd-111">语法</span><span class="sxs-lookup"><span data-stu-id="96ffd-111">Syntax</span></span>  
  
```  
peverify filename [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="96ffd-112">参数</span><span class="sxs-lookup"><span data-stu-id="96ffd-112">Parameters</span></span>  
  
|<span data-ttu-id="96ffd-113">参数</span><span class="sxs-lookup"><span data-stu-id="96ffd-113">Argument</span></span>|<span data-ttu-id="96ffd-114">描述</span><span class="sxs-lookup"><span data-stu-id="96ffd-114">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="96ffd-115">*filename*</span><span class="sxs-lookup"><span data-stu-id="96ffd-115">*filename*</span></span>|<span data-ttu-id="96ffd-116">要为其检查 MSIL 和元数据的可移植可执行 (PE) 文件。</span><span class="sxs-lookup"><span data-stu-id="96ffd-116">The portable executable (PE) file for which to check the MSIL and metadata.</span></span>|  
  
|<span data-ttu-id="96ffd-117">选项</span><span class="sxs-lookup"><span data-stu-id="96ffd-117">Option</span></span>|<span data-ttu-id="96ffd-118">描述</span><span class="sxs-lookup"><span data-stu-id="96ffd-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="96ffd-119">/break= maxErrorCount</span><span class="sxs-lookup"><span data-stu-id="96ffd-119">**/break=** *maxErrorCount*</span></span>|<span data-ttu-id="96ffd-120">在出现 maxErrorCount 错误后中止验证。</span><span class="sxs-lookup"><span data-stu-id="96ffd-120">Aborts verification after *maxErrorCount* errors.</span></span><br /><br /> <span data-ttu-id="96ffd-121">此参数在 .NET Framework 2.0 版或更高版本中不受支持。</span><span class="sxs-lookup"><span data-stu-id="96ffd-121">This parameter is not supported in .NET Framework version 2.0 or later.</span></span>|  
|<span data-ttu-id="96ffd-122">**/clock**</span><span class="sxs-lookup"><span data-stu-id="96ffd-122">**/clock**</span></span>|<span data-ttu-id="96ffd-123">测量并报告下列验证时间（以毫秒为单位）：</span><span class="sxs-lookup"><span data-stu-id="96ffd-123">Measures and reports the following verification times in milliseconds:</span></span><br /><br /> <span data-ttu-id="96ffd-124">MD Val. cycle</span><span class="sxs-lookup"><span data-stu-id="96ffd-124">**MD Val. cycle**</span></span><br /> <span data-ttu-id="96ffd-125">元数据验证周期</span><span class="sxs-lookup"><span data-stu-id="96ffd-125">Metadata validation cycle</span></span><br /><br /> <span data-ttu-id="96ffd-126">MD Val. pure</span><span class="sxs-lookup"><span data-stu-id="96ffd-126">**MD Val. pure**</span></span><br /> <span data-ttu-id="96ffd-127">元数据纯验证</span><span class="sxs-lookup"><span data-stu-id="96ffd-127">Metadata validation pure</span></span><br /><br /> <span data-ttu-id="96ffd-128">IL Ver. cycle</span><span class="sxs-lookup"><span data-stu-id="96ffd-128">**IL Ver. cycle**</span></span><br /> <span data-ttu-id="96ffd-129">Microsoft 中间语言 (MSIL) 验证周期</span><span class="sxs-lookup"><span data-stu-id="96ffd-129">Microsoft intermediate language (MSIL) verification cycle</span></span><br /><br /> <span data-ttu-id="96ffd-130">IL Ver pure</span><span class="sxs-lookup"><span data-stu-id="96ffd-130">**IL Ver pure**</span></span><br /> <span data-ttu-id="96ffd-131">MSIL 纯验证</span><span class="sxs-lookup"><span data-stu-id="96ffd-131">MSIL verification pure</span></span><br /><br /> <span data-ttu-id="96ffd-132">MD Val. cycle 和 IL Ver. cycle 时间包括执行必要的启动和关闭过程所需的时间。</span><span class="sxs-lookup"><span data-stu-id="96ffd-132">The **MD Val. cycle** and **IL Ver. cycle** times include the time required to perform necessary startup and shutdown procedures.</span></span> <span data-ttu-id="96ffd-133">MD Val. pure 和 IL Ver pure 时间反映了只执行验证或检验所需的时间。</span><span class="sxs-lookup"><span data-stu-id="96ffd-133">The **MD Val. pure** and **IL Ver pure** times reflect the time required to perform the validation or verification only.</span></span>|  
|<span data-ttu-id="96ffd-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="96ffd-134">**/help**</span></span>|<span data-ttu-id="96ffd-135">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="96ffd-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="96ffd-136">/hresult</span><span class="sxs-lookup"><span data-stu-id="96ffd-136">**/hresult**</span></span>|<span data-ttu-id="96ffd-137">以十六进制格式显示错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-137">Displays error codes in hexadecimal format.</span></span>|  
|<span data-ttu-id="96ffd-138">/ignore= hex.code [, hex.code]</span><span class="sxs-lookup"><span data-stu-id="96ffd-138">**/ignore=** *hex.code* [, *hex.code*]</span></span>|<span data-ttu-id="96ffd-139">忽略指定的错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-139">Ignores the specified error codes.</span></span>|  
|<span data-ttu-id="96ffd-140">/ignore=@ responseFile</span><span class="sxs-lookup"><span data-stu-id="96ffd-140">**/ignore=@** *responseFile*</span></span>|<span data-ttu-id="96ffd-141">忽略在指定响应文件中列出的错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-141">Ignores the error codes listed in the specified response file.</span></span>|  
|<span data-ttu-id="96ffd-142">/il</span><span class="sxs-lookup"><span data-stu-id="96ffd-142">**/il**</span></span>|<span data-ttu-id="96ffd-143">针对在由 filename 指定的程序集中实现的方法执行 MSIL 类型安全验证检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-143">Performs MSIL type safety verification checks for methods implemented in the assembly specified by *filename*.</span></span> <span data-ttu-id="96ffd-144">除非指定 /quiet 选项，否则此工具将为发现的每个问题返回详细的说明。</span><span class="sxs-lookup"><span data-stu-id="96ffd-144">The tool returns detailed descriptions for each problem found unless you specify the **/quiet** option.</span></span>|  
|<span data-ttu-id="96ffd-145">/md</span><span class="sxs-lookup"><span data-stu-id="96ffd-145">**/md**</span></span>|<span data-ttu-id="96ffd-146">针对由 filename 指定的程序集执行元数据验证检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-146">Performs metadata validation checks on the assembly specified by *filename*.</span></span> <span data-ttu-id="96ffd-147">这将遍历文件中的整个元数据结构并报告遇到的所有验证问题。</span><span class="sxs-lookup"><span data-stu-id="96ffd-147">This walks the full metadata structure within the file and reports all validation problems encountered.</span></span>|  
|<span data-ttu-id="96ffd-148">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="96ffd-148">**/nologo**</span></span>|<span data-ttu-id="96ffd-149">禁止显示产品版本和版权信息。</span><span class="sxs-lookup"><span data-stu-id="96ffd-149">Suppresses the display of product version and copyright information.</span></span>|  
|<span data-ttu-id="96ffd-150">/nosymbols</span><span class="sxs-lookup"><span data-stu-id="96ffd-150">**/nosymbols**</span></span>|<span data-ttu-id="96ffd-151">在 .NET Framework 2.0 版中，禁止显示行号以便向后兼容。</span><span class="sxs-lookup"><span data-stu-id="96ffd-151">In the .NET Framework version 2.0, suppresses line numbers for backward compatibility.</span></span>|  
|<span data-ttu-id="96ffd-152">**/quiet**</span><span class="sxs-lookup"><span data-stu-id="96ffd-152">**/quiet**</span></span>|<span data-ttu-id="96ffd-153">指定安静模式；禁止显示验证问题报告的输出。</span><span class="sxs-lookup"><span data-stu-id="96ffd-153">Specifies quiet mode; suppresses output of the verification problem reports.</span></span> <span data-ttu-id="96ffd-154">Peverify.exe 仍将报告文件是否是类型安全的，但不会报告关于阻止类型安全验证的问题的信息。</span><span class="sxs-lookup"><span data-stu-id="96ffd-154">Peverify.exe still reports whether the file is type safe, but does not report information on problems preventing type safety verification.</span></span>|  
|`/transparent`|<span data-ttu-id="96ffd-155">仅验证透明方法。</span><span class="sxs-lookup"><span data-stu-id="96ffd-155">Verify only the transparent methods.</span></span>|  
|<span data-ttu-id="96ffd-156">/unique</span><span class="sxs-lookup"><span data-stu-id="96ffd-156">**/unique**</span></span>|<span data-ttu-id="96ffd-157">忽略重复的错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-157">Ignores repeating error codes.</span></span>|  
|<span data-ttu-id="96ffd-158">**/verbose**</span><span class="sxs-lookup"><span data-stu-id="96ffd-158">**/verbose**</span></span>|<span data-ttu-id="96ffd-159">在 .NET Framework 2.0 版中，显示 MSIL 验证消息中的附加信息。</span><span class="sxs-lookup"><span data-stu-id="96ffd-159">In the .NET Framework version 2.0, displays additional information in MSIL verification messages.</span></span>|  
|<span data-ttu-id="96ffd-160">**/?**</span><span class="sxs-lookup"><span data-stu-id="96ffd-160">**/?**</span></span>|<span data-ttu-id="96ffd-161">显示该工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="96ffd-161">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96ffd-162">备注</span><span class="sxs-lookup"><span data-stu-id="96ffd-162">Remarks</span></span>  
 <span data-ttu-id="96ffd-163">公共语言运行时依赖应用程序代码的类型安全执行，以帮助强制实施安全性和隔离机制。</span><span class="sxs-lookup"><span data-stu-id="96ffd-163">The common language runtime relies on the type-safe execution of application code to help enforce security and isolation mechanisms.</span></span> <span data-ttu-id="96ffd-164">通常情况下，虽然可以设置安全策略以允许执行受信任但不可验证的代码，但无法运行不是[可验证类型安全](https://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc)的代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-164">Normally, code that is not [verifiably type safe](https://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc) cannot run, although you can set security policy to allow the execution of trusted but unverifiable code.</span></span>  
  
 <span data-ttu-id="96ffd-165">如果既未指定 /md 选项也未指定 /il 选项，则 Peverify.exe 将执行两种类型的检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-165">If neither the **/md** nor **/il** options are specified, Peverify.exe performs both types of checks.</span></span> <span data-ttu-id="96ffd-166">Peverify.exe 首先执行 /md 检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-166">Peverify.exe performs **/md** checks first.</span></span> <span data-ttu-id="96ffd-167">如果没有错误，则执行 /il 检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-167">If there are no errors, **/il** checks are made.</span></span> <span data-ttu-id="96ffd-168">如果同时指定了 /md 和 /il，则即使元数据中存在错误，也执行 /il 检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-168">If you specify both **/md** and **/il**, **/il** checks are made even if there are errors in the metadata.</span></span> <span data-ttu-id="96ffd-169">因此，如果没有元数据错误，则 peverify filename 等效于 peverify filename /md /il。</span><span class="sxs-lookup"><span data-stu-id="96ffd-169">Thus, if there are no metadata errors, **peverify** *filename* is equivalent to **peverify** *filename* **/md** **/il**.</span></span>  
  
 <span data-ttu-id="96ffd-170">Peverify.exe 基于数据流分析和一个包含数百条有关有效元数据的规则的列表来执行全面的 MSIL 验证检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-170">Peverify.exe performs comprehensive MSIL verification checks based on dataflow analysis plus a list of several hundred rules on valid metadata.</span></span> <span data-ttu-id="96ffd-171">有关 Peverify.exe 执行的检查的详细信息，请参见 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 中“Tools Developers Guide”文件夹中的“元数据验证规范”和“MSIL 指令集规范”。</span><span class="sxs-lookup"><span data-stu-id="96ffd-171">For detailed information on the checks Peverify.exe performs, see the "Metadata Validation Specification" and the "MSIL Instruction Set Specification" in the Tools Developers Guide folder in the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>  
  
 <span data-ttu-id="96ffd-172">注意，.NET Framework 2.0 版或更高版本支持使用如下 MSIL 指令指定的可验证 `byref` 返回值：`dup`、`ldsflda`、`ldflda`、`ldelema`、`call` 和 `unbox`。</span><span class="sxs-lookup"><span data-stu-id="96ffd-172">Note that the .NET Framework version 2.0 or later supports verifiable `byref` returns specified using the following MSIL instructions: `dup`, `ldsflda`, `ldflda`, `ldelema`, `call` and `unbox`.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="96ffd-173">示例</span><span class="sxs-lookup"><span data-stu-id="96ffd-173">Examples</span></span>  
 <span data-ttu-id="96ffd-174">下面的命令为在 `myAssembly.exe` 程序集中实现的方法执行元数据验证检查和 MSIL 类型安全验证检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-174">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span>  
  
```  
peverify myAssembly.exe /md /il  
```  
  
 <span data-ttu-id="96ffd-175">上述请求成功完成后，Peverify.exe 将显示下面的消息。</span><span class="sxs-lookup"><span data-stu-id="96ffd-175">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
```  
  
 <span data-ttu-id="96ffd-176">下面的命令为在 `myAssembly.exe` 程序集中实现的方法执行元数据验证检查和 MSIL 类型安全验证检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-176">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="96ffd-177">此工具显示执行这些检查所需的时间。</span><span class="sxs-lookup"><span data-stu-id="96ffd-177">The tool displays the time required to perform these checks.</span></span>  
  
```  
peverify myAssembly.exe /md /il /clock  
```  
  
 <span data-ttu-id="96ffd-178">上述请求成功完成后，Peverify.exe 将显示下面的消息。</span><span class="sxs-lookup"><span data-stu-id="96ffd-178">Upon successful completion of the above request, Peverify.exe displays the following message.</span></span>  
  
```  
All classes and methods in myAssembly.exe Verified  
Timing: Total run     320 msec  
        MD Val.cycle  40 msec  
        MD Val.pure   10 msec  
        IL Ver.cycle  270 msec  
        IL Ver.pure   230 msec  
```  
  
 <span data-ttu-id="96ffd-179">下面的命令为在 `myAssembly.exe` 程序集中实现的方法执行元数据验证检查和 MSIL 类型安全验证检查。</span><span class="sxs-lookup"><span data-stu-id="96ffd-179">The following command performs metadata validation checks and MSIL type safety verification checks for methods implemented in the assembly `myAssembly.exe`.</span></span> <span data-ttu-id="96ffd-180">但是，Peverify.exe 会在达到最大错误计数 100 时停止。</span><span class="sxs-lookup"><span data-stu-id="96ffd-180">Peverify.exe stops, however, when it reaches the maximum error count of 100.</span></span> <span data-ttu-id="96ffd-181">该工具也忽略指定的错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-181">The tool also ignores the specified error codes.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore=0x12345678,0xABCD1234  
```  
  
 <span data-ttu-id="96ffd-182">下面的命令与上一个示例产生同样的结果，但指定要在响应文件 `ignoreErrors.rsp` 中忽略的错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-182">The following command produces the same result as the above previous example, but specifies the error codes to ignore in the response file `ignoreErrors.rsp`.</span></span>  
  
```  
peverify myAssembly.exe /break=100 /ignore@ignoreErrors.rsp  
```  
  
 <span data-ttu-id="96ffd-183">响应文件可以包含一个用逗号分隔的错误代码列表。</span><span class="sxs-lookup"><span data-stu-id="96ffd-183">The response file can contain a comma-separated list of error codes.</span></span>  
  
```  
0x12345678, 0xABCD1234  
```  
  
 <span data-ttu-id="96ffd-184">或者，可将响应文件的格式设置为每行一个错误代码。</span><span class="sxs-lookup"><span data-stu-id="96ffd-184">Alternatively, the response file can be formatted with one error code per line.</span></span>  
  
```  
0x12345678  
0xABCD1234  
```  
  
## <a name="see-also"></a><span data-ttu-id="96ffd-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="96ffd-185">See Also</span></span>  
 [<span data-ttu-id="96ffd-186">工具</span><span class="sxs-lookup"><span data-stu-id="96ffd-186">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="96ffd-187">NIB：编写可验证类型安全代码</span><span class="sxs-lookup"><span data-stu-id="96ffd-187">NIB: Writing Verifiably Type-Safe Code</span></span>](https://msdn.microsoft.com/library/d18f10ef-3b48-4f47-8726-96714021547b)  
 [<span data-ttu-id="96ffd-188">类型安全和安全性</span><span class="sxs-lookup"><span data-stu-id="96ffd-188">Type Safety and Security</span></span>](https://msdn.microsoft.com/library/095cd1f6-d8db-4c0e-bce2-83ccb34dd5dc)  
 [<span data-ttu-id="96ffd-189">命令提示</span><span class="sxs-lookup"><span data-stu-id="96ffd-189">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
