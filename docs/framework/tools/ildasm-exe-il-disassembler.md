---
title: Ildasm.exe（IL 反汇编程序）
ms.date: 03/30/2017
helpviewer_keywords:
- PE files, MSIL Disassembler
- portable executable files, MSIL Disassembler
- Ildasm.exe
- MSIL Disassembler
- text files produced by MSIL Disassembler
- disassembling file for MSIL Assembler input
ms.assetid: db27f6b2-f1ec-499e-be3a-7eecf95ca42b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b8b69544b2d8041a3aa4cb566867b6c14b29f0f8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409105"
---
# <a name="ildasmexe-il-disassembler"></a><span data-ttu-id="3de89-102">Ildasm.exe（IL 反汇编程序）</span><span class="sxs-lookup"><span data-stu-id="3de89-102">Ildasm.exe (IL Disassembler)</span></span>

<span data-ttu-id="3de89-103">IL 反汇编程序是 IL 汇编程序 (Ilasm.exe) 的配套工具。</span><span class="sxs-lookup"><span data-stu-id="3de89-103">The IL Disassembler is a companion tool to the IL Assembler (*Ilasm.exe*).</span></span> <span data-ttu-id="3de89-104">Ildasm.exe 可利用包含中间语言 (IL) 代码的可移植可执行 (PE) 文件，并创建适合输入到 Ilasm.exe 的文本文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-104">*Ildasm.exe* takes a portable executable (PE) file that contains intermediate language (IL) code and creates a text file suitable as input to *Ilasm.exe*.</span></span>

<span data-ttu-id="3de89-105">此工具会自动随 Visual Studio 一起安装。</span><span class="sxs-lookup"><span data-stu-id="3de89-105">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="3de89-106">若要运行此工具，请使用开发人员命令提示（或 Windows 7 中的 Visual Studio 命令提示）。</span><span class="sxs-lookup"><span data-stu-id="3de89-106">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="3de89-107">有关详细信息，请参阅[命令提示](../../../docs/framework/tools/developer-command-prompt-for-vs.md)。</span><span class="sxs-lookup"><span data-stu-id="3de89-107">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>

<span data-ttu-id="3de89-108">在命令提示符处，键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="3de89-108">At the command prompt, type the following:</span></span>

## <a name="syntax"></a><span data-ttu-id="3de89-109">语法</span><span class="sxs-lookup"><span data-stu-id="3de89-109">Syntax</span></span>

```
ildasm [options] [PEfilename] [options]
```

#### <a name="parameters"></a><span data-ttu-id="3de89-110">参数</span><span class="sxs-lookup"><span data-stu-id="3de89-110">Parameters</span></span>

<span data-ttu-id="3de89-111">下列选项可用于 .exe、.dll、.obj、.lib 和 .winmd 文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-111">The following options are available for *.exe*, *.dll*, *.obj*, *.lib*, and *.winmd* files.</span></span>

| <span data-ttu-id="3de89-112">选项</span><span class="sxs-lookup"><span data-stu-id="3de89-112">Option</span></span> | <span data-ttu-id="3de89-113">描述</span><span class="sxs-lookup"><span data-stu-id="3de89-113">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="3de89-114">**/out=** `filename`</span><span class="sxs-lookup"><span data-stu-id="3de89-114">**/out=** `filename`</span></span>|<span data-ttu-id="3de89-115">创建具有指定 `filename` 的输出文件，而不是在图形用户界面中显示结果。</span><span class="sxs-lookup"><span data-stu-id="3de89-115">Creates an output file with the specified `filename`, rather than displaying the results in a graphical user interface.</span></span>|
|<span data-ttu-id="3de89-116">/rtf</span><span class="sxs-lookup"><span data-stu-id="3de89-116">**/rtf**</span></span>|<span data-ttu-id="3de89-117">以 RTF 格式生成输出。</span><span class="sxs-lookup"><span data-stu-id="3de89-117">Produces output in rich text format.</span></span> <span data-ttu-id="3de89-118">与 /text 选项一起使用时无效。</span><span class="sxs-lookup"><span data-stu-id="3de89-118">Invalid with the **/text** option.</span></span>|
|<span data-ttu-id="3de89-119">/text</span><span class="sxs-lookup"><span data-stu-id="3de89-119">**/text**</span></span>|<span data-ttu-id="3de89-120">将结果显示到控制台窗口，而不是显示在图形用户界面中或显示为输出文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-120">Displays the results to the console window, rather than in a graphical user interface or as an output file.</span></span>|
|<span data-ttu-id="3de89-121">/html</span><span class="sxs-lookup"><span data-stu-id="3de89-121">**/html**</span></span>|<span data-ttu-id="3de89-122">以 HTML 格式生成输出。</span><span class="sxs-lookup"><span data-stu-id="3de89-122">Produces output in HTML format.</span></span> <span data-ttu-id="3de89-123">与 /output 选项一起使用时才有效。</span><span class="sxs-lookup"><span data-stu-id="3de89-123">Valid with the **/output** option only.</span></span>|
|<span data-ttu-id="3de89-124">**/?**</span><span class="sxs-lookup"><span data-stu-id="3de89-124">**/?**</span></span>|<span data-ttu-id="3de89-125">显示此工具的命令语法和选项。</span><span class="sxs-lookup"><span data-stu-id="3de89-125">Displays the command syntax and options for the tool.</span></span>|

<span data-ttu-id="3de89-126">下列附加选项可用于 .exe、.dll 和 .winmd 文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-126">The following additional options are available for *.exe*, *.dll*, and *.winmd* files.</span></span>

| <span data-ttu-id="3de89-127">选项</span><span class="sxs-lookup"><span data-stu-id="3de89-127">Option</span></span> | <span data-ttu-id="3de89-128">描述</span><span class="sxs-lookup"><span data-stu-id="3de89-128">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="3de89-129">/bytes</span><span class="sxs-lookup"><span data-stu-id="3de89-129">**/bytes**</span></span>|<span data-ttu-id="3de89-130">以十六进制格式显示作为指令注释的实际字节。</span><span class="sxs-lookup"><span data-stu-id="3de89-130">Shows actual bytes, in hexadecimal format, as instruction comments.</span></span>|
|<span data-ttu-id="3de89-131">/caverbal</span><span class="sxs-lookup"><span data-stu-id="3de89-131">**/caverbal**</span></span>|<span data-ttu-id="3de89-132">以文字形式生成自定义特性 Blob。</span><span class="sxs-lookup"><span data-stu-id="3de89-132">Produces custom attribute blobs in verbal form.</span></span> <span data-ttu-id="3de89-133">默认为二进制形式。</span><span class="sxs-lookup"><span data-stu-id="3de89-133">The default is binary form.</span></span>|
|<span data-ttu-id="3de89-134">/linenum</span><span class="sxs-lookup"><span data-stu-id="3de89-134">**/linenum**</span></span>|<span data-ttu-id="3de89-135">包含对原始源行的引用。</span><span class="sxs-lookup"><span data-stu-id="3de89-135">Includes references to original source lines.</span></span>|
|<span data-ttu-id="3de89-136">/nobar</span><span class="sxs-lookup"><span data-stu-id="3de89-136">**/nobar**</span></span>|<span data-ttu-id="3de89-137">禁止显示反汇编进度指示器弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="3de89-137">Suppresses the disassembly progress indicator pop-up window.</span></span>|
|<span data-ttu-id="3de89-138">/noca</span><span class="sxs-lookup"><span data-stu-id="3de89-138">**/noca**</span></span>|<span data-ttu-id="3de89-139">禁止显示自定义特性的输出。</span><span class="sxs-lookup"><span data-stu-id="3de89-139">Suppresses the output of custom attributes.</span></span>|
|<span data-ttu-id="3de89-140">/project</span><span class="sxs-lookup"><span data-stu-id="3de89-140">**/project**</span></span>|<span data-ttu-id="3de89-141">以托管代码的方式显示元数据，而不是以本机 [!INCLUDE[wrt](../../../includes/wrt-md.md)]的方式显示。</span><span class="sxs-lookup"><span data-stu-id="3de89-141">Displays metadata the way it appears to managed code, instead of the way it appears in the native [!INCLUDE[wrt](../../../includes/wrt-md.md)].</span></span> <span data-ttu-id="3de89-142">如果 `PEfilename` 不是 Windows 元数据 (.winmd) 文件，此选项将不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="3de89-142">If `PEfilename` is not a Windows metadata (*.winmd*) file, this option has no effect.</span></span> <span data-ttu-id="3de89-143">请参阅 [Windows 应用商店应用和 Windows 运行时的 .NET Framework 支持](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="3de89-143">See [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).</span></span>|
|<span data-ttu-id="3de89-144">/pubonly</span><span class="sxs-lookup"><span data-stu-id="3de89-144">**/pubonly**</span></span>|<span data-ttu-id="3de89-145">仅反汇编公共类型和公共成员。</span><span class="sxs-lookup"><span data-stu-id="3de89-145">Disassembles only public types and members.</span></span> <span data-ttu-id="3de89-146">等效于 /visibility:PUB。</span><span class="sxs-lookup"><span data-stu-id="3de89-146">Equivalent to **/visibility:PUB**.</span></span>|
|<span data-ttu-id="3de89-147">/quoteallnames</span><span class="sxs-lookup"><span data-stu-id="3de89-147">**/quoteallnames**</span></span>|<span data-ttu-id="3de89-148">在单引号中包含所有名称。</span><span class="sxs-lookup"><span data-stu-id="3de89-148">Includes all names in single quotes.</span></span>|
|<span data-ttu-id="3de89-149">/raweh</span><span class="sxs-lookup"><span data-stu-id="3de89-149">**/raweh**</span></span>|<span data-ttu-id="3de89-150">以原始格式显示异常处理子句。</span><span class="sxs-lookup"><span data-stu-id="3de89-150">Shows exception handling clauses in raw form.</span></span>|
|<span data-ttu-id="3de89-151">/source</span><span class="sxs-lookup"><span data-stu-id="3de89-151">**/source**</span></span>|<span data-ttu-id="3de89-152">以注释形式显示原始源行。</span><span class="sxs-lookup"><span data-stu-id="3de89-152">Shows original source lines as comments.</span></span>|
|<span data-ttu-id="3de89-153">/tokens</span><span class="sxs-lookup"><span data-stu-id="3de89-153">**/tokens**</span></span>|<span data-ttu-id="3de89-154">显示类和成员的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="3de89-154">Shows metadata tokens of classes and members.</span></span>|
|<span data-ttu-id="3de89-155">**/visibility:** `vis`[+`vis`...]</span><span class="sxs-lookup"><span data-stu-id="3de89-155">**/visibility:** `vis`[+`vis`...]</span></span>|<span data-ttu-id="3de89-156">仅反汇编具有指定可见性的类型或成员。</span><span class="sxs-lookup"><span data-stu-id="3de89-156">Disassembles only types or members with the specified visibility.</span></span> <span data-ttu-id="3de89-157">下面是 `vis` 的有效值：</span><span class="sxs-lookup"><span data-stu-id="3de89-157">The following are valid values for `vis`:</span></span><br /><br /> <span data-ttu-id="3de89-158">PUB - 公共</span><span class="sxs-lookup"><span data-stu-id="3de89-158">**PUB** — Public</span></span><br /><br /> <span data-ttu-id="3de89-159">PRI - 私有</span><span class="sxs-lookup"><span data-stu-id="3de89-159">**PRI** — Private</span></span><br /><br /> <span data-ttu-id="3de89-160">FAM - 系列</span><span class="sxs-lookup"><span data-stu-id="3de89-160">**FAM** — Family</span></span><br /><br /> <span data-ttu-id="3de89-161">ASM - 程序集</span><span class="sxs-lookup"><span data-stu-id="3de89-161">**ASM** — Assembly</span></span><br /><br /> <span data-ttu-id="3de89-162">FAA - 系列和程序集</span><span class="sxs-lookup"><span data-stu-id="3de89-162">**FAA** — Family and Assembly</span></span><br /><br /> <span data-ttu-id="3de89-163">FOA - 系列或程序集</span><span class="sxs-lookup"><span data-stu-id="3de89-163">**FOA** — Family or Assembly</span></span><br /><br /> <span data-ttu-id="3de89-164">PSC - 私有范围</span><span class="sxs-lookup"><span data-stu-id="3de89-164">**PSC** — Private Scope</span></span><br /><br /> <span data-ttu-id="3de89-165">有关这些可见性修饰符的定义，请参见 <xref:System.Reflection.MethodAttributes> 和 <xref:System.Reflection.TypeAttributes>。</span><span class="sxs-lookup"><span data-stu-id="3de89-165">For definitions of these visibility modifiers, see <xref:System.Reflection.MethodAttributes> and <xref:System.Reflection.TypeAttributes>.</span></span>|

<span data-ttu-id="3de89-166">下列选项仅对用于文件或控制台输出的 .exe、.dll 和 .winmd 文件有效。</span><span class="sxs-lookup"><span data-stu-id="3de89-166">The following options are valid for *.exe*, *.dll*, and *.winmd* files for file or console output only.</span></span>

| <span data-ttu-id="3de89-167">选项</span><span class="sxs-lookup"><span data-stu-id="3de89-167">Option</span></span> | <span data-ttu-id="3de89-168">描述</span><span class="sxs-lookup"><span data-stu-id="3de89-168">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="3de89-169">**/all**</span><span class="sxs-lookup"><span data-stu-id="3de89-169">**/all**</span></span>|<span data-ttu-id="3de89-170">指定 /header、/bytes、/stats、/classlist 和 /tokens 选项的组合。</span><span class="sxs-lookup"><span data-stu-id="3de89-170">Specifies a combination of the **/header**, **/bytes**, **/stats**, **/classlist**, and **/tokens** options.</span></span>|
|<span data-ttu-id="3de89-171">/classlist</span><span class="sxs-lookup"><span data-stu-id="3de89-171">**/classlist**</span></span>|<span data-ttu-id="3de89-172">包含模块中定义的类的列表。</span><span class="sxs-lookup"><span data-stu-id="3de89-172">Includes a list of classes defined in the module.</span></span>|
|<span data-ttu-id="3de89-173">/forward</span><span class="sxs-lookup"><span data-stu-id="3de89-173">**/forward**</span></span>|<span data-ttu-id="3de89-174">使用前向类声明。</span><span class="sxs-lookup"><span data-stu-id="3de89-174">Uses forward class declaration.</span></span>|
|<span data-ttu-id="3de89-175">/headers</span><span class="sxs-lookup"><span data-stu-id="3de89-175">**/headers**</span></span>|<span data-ttu-id="3de89-176">在输出中包含文件头信息。</span><span class="sxs-lookup"><span data-stu-id="3de89-176">Includes file header information in the output.</span></span>|
|<span data-ttu-id="3de89-177">**/item:** `class`[**::** `member`[`(sig`]]</span><span class="sxs-lookup"><span data-stu-id="3de89-177">**/item:** `class`[**::** `member`[`(sig`]]</span></span>|<span data-ttu-id="3de89-178">根据所提供的自变量反汇编下列内容：</span><span class="sxs-lookup"><span data-stu-id="3de89-178">Disassembles the following depending upon the argument supplied:</span></span><br /><br /> <span data-ttu-id="3de89-179">-   反汇编指定的 `class`。</span><span class="sxs-lookup"><span data-stu-id="3de89-179">-   Disassembles the specified `class`.</span></span><br /><span data-ttu-id="3de89-180">-   反汇编类的指定 `class` 的 `member`。</span><span class="sxs-lookup"><span data-stu-id="3de89-180">-   Disassembles the specified `member` of the `class`.</span></span><br /><span data-ttu-id="3de89-181">-   反汇编具有指定签名 `sig` 的 `class` 的 `member`。</span><span class="sxs-lookup"><span data-stu-id="3de89-181">-   Disassembles the `member` of the `class` with the specified signature `sig`.</span></span> <span data-ttu-id="3de89-182">`sig` 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="3de89-182">The format of `sig` is:</span></span><br />     <span data-ttu-id="3de89-183">[`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)</span><span class="sxs-lookup"><span data-stu-id="3de89-183">[`instance`] `returnType`(`parameterType1`, `parameterType2`, …, `parameterTypeN`)</span></span><br />     <span data-ttu-id="3de89-184">请注意：在 .NET Framework 1.0 和 1.1 版中，`sig` 必须后跟右括号：`(sig)`。</span><span class="sxs-lookup"><span data-stu-id="3de89-184">**Note** In the .NET Framework versions 1.0 and 1.1, `sig` must be followed by a closing parenthesis: `(sig)`.</span></span> <span data-ttu-id="3de89-185">从 .NET Framework 2.0 开始，必须省略右括号：(`sig`。</span><span class="sxs-lookup"><span data-stu-id="3de89-185">Starting with the Net Framework 2.0 the closing parenthesis must be omitted: (`sig`.</span></span>|
|<span data-ttu-id="3de89-186">/noil</span><span class="sxs-lookup"><span data-stu-id="3de89-186">**/noil**</span></span>|<span data-ttu-id="3de89-187">禁止显示 IL 程序集代码输出。</span><span class="sxs-lookup"><span data-stu-id="3de89-187">Suppresses IL assembly code output.</span></span>|
|<span data-ttu-id="3de89-188">/stats</span><span class="sxs-lookup"><span data-stu-id="3de89-188">**/stats**</span></span>|<span data-ttu-id="3de89-189">包含映像的统计信息。</span><span class="sxs-lookup"><span data-stu-id="3de89-189">Includes statistics on the image.</span></span>|
|<span data-ttu-id="3de89-190">/typelist</span><span class="sxs-lookup"><span data-stu-id="3de89-190">**/typelist**</span></span>|<span data-ttu-id="3de89-191">生成类型的完整列表，以便在往返过程中保留类型排序。</span><span class="sxs-lookup"><span data-stu-id="3de89-191">Produces the full list of types, to preserve type ordering in a round trip.</span></span>|
|<span data-ttu-id="3de89-192">/unicode</span><span class="sxs-lookup"><span data-stu-id="3de89-192">**/unicode**</span></span>|<span data-ttu-id="3de89-193">对输出使用 Unicode 编码。</span><span class="sxs-lookup"><span data-stu-id="3de89-193">Uses Unicode encoding for the output.</span></span>|
|<span data-ttu-id="3de89-194">/utf8</span><span class="sxs-lookup"><span data-stu-id="3de89-194">**/utf8**</span></span>|<span data-ttu-id="3de89-195">对输出使用 UTF-8 编码。</span><span class="sxs-lookup"><span data-stu-id="3de89-195">Uses UTF-8 encoding for the output.</span></span> <span data-ttu-id="3de89-196">ANSI 为默认值。</span><span class="sxs-lookup"><span data-stu-id="3de89-196">ANSI is the default.</span></span>|

<span data-ttu-id="3de89-197">下列选项仅对用于文件或控制台输出的 .exe、.dll、.obj、.lib 和 .winmd 文件有效。</span><span class="sxs-lookup"><span data-stu-id="3de89-197">The following options are valid for *.exe*, *.dll*, *.obj*, *.lib*, and *.winmd* files for file or console output only.</span></span>

| <span data-ttu-id="3de89-198">选项</span><span class="sxs-lookup"><span data-stu-id="3de89-198">Option</span></span> | <span data-ttu-id="3de89-199">描述</span><span class="sxs-lookup"><span data-stu-id="3de89-199">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="3de89-200">/metadata[=`specifier`]</span><span class="sxs-lookup"><span data-stu-id="3de89-200">**/metadata**[=`specifier`]</span></span>|<span data-ttu-id="3de89-201">显示元数据，其中 `specifier` 为：</span><span class="sxs-lookup"><span data-stu-id="3de89-201">Shows metadata, where `specifier` is:</span></span><br /><br /> <span data-ttu-id="3de89-202">MDHEADER - 显示元数据头信息和大小。</span><span class="sxs-lookup"><span data-stu-id="3de89-202">**MDHEADER** — Show the metadata header information and sizes.</span></span><br /><br /> <span data-ttu-id="3de89-203">HEX - 以十六进制形式及文字形式显示信息。</span><span class="sxs-lookup"><span data-stu-id="3de89-203">**HEX** — Show information in hex as well as in words.</span></span><br /><br /> <span data-ttu-id="3de89-204">CSV - 显示记录计数和堆大小。</span><span class="sxs-lookup"><span data-stu-id="3de89-204">**CSV** — Show the record counts and heap sizes.</span></span><br /><br /> <span data-ttu-id="3de89-205">UNREX - 显示无法解析的外部对象。</span><span class="sxs-lookup"><span data-stu-id="3de89-205">**UNREX** — Show unresolved externals.</span></span><br /><br /> <span data-ttu-id="3de89-206">SCHEMA - 显示元数据头和架构信息。</span><span class="sxs-lookup"><span data-stu-id="3de89-206">**SCHEMA** — Show the metadata header and schema information.</span></span><br /><br /> <span data-ttu-id="3de89-207">RAW - 显示原始元数据表。</span><span class="sxs-lookup"><span data-stu-id="3de89-207">**RAW** — Show the raw metadata tables.</span></span><br /><br /> <span data-ttu-id="3de89-208">HEAPS - 显示原始堆。</span><span class="sxs-lookup"><span data-stu-id="3de89-208">**HEAPS** — Show the raw heaps.</span></span><br /><br /> <span data-ttu-id="3de89-209">VALIDATE - 验证元数据的一致性。</span><span class="sxs-lookup"><span data-stu-id="3de89-209">**VALIDATE** — Validate the consistency of the metadata.</span></span><br /><br /> <span data-ttu-id="3de89-210">可多次指定 /metadata，并为 `specifier` 指定不同的值。</span><span class="sxs-lookup"><span data-stu-id="3de89-210">You can specify **/metadata** multiple times, with different values for `specifier`.</span></span>|

<span data-ttu-id="3de89-211">下列选项仅对用于文件或控制台输出的 .lib 文件有效。</span><span class="sxs-lookup"><span data-stu-id="3de89-211">The following options are valid for *.lib* files for file or console output only.</span></span>

| <span data-ttu-id="3de89-212">选项</span><span class="sxs-lookup"><span data-stu-id="3de89-212">Option</span></span> | <span data-ttu-id="3de89-213">描述</span><span class="sxs-lookup"><span data-stu-id="3de89-213">Description</span></span> |
| ------ | ----------- |
|<span data-ttu-id="3de89-214">/objectfile=`filename`</span><span class="sxs-lookup"><span data-stu-id="3de89-214">**/objectfile**=`filename`</span></span>|<span data-ttu-id="3de89-215">显示指定库中单个对象文件的元数据。</span><span class="sxs-lookup"><span data-stu-id="3de89-215">Shows the metadata of a single object file in the specified library.</span></span>|

> [!NOTE]
> <span data-ttu-id="3de89-216">Ildasm.exe 的所有选项都不区分大小写，并且根据前三个字母识别。</span><span class="sxs-lookup"><span data-stu-id="3de89-216">All options for *Ildasm.exe* are case-insensitive and recognized by the first three letters.</span></span> <span data-ttu-id="3de89-217">例如，/quo 等效于 /quoteallnames。</span><span class="sxs-lookup"><span data-stu-id="3de89-217">For example, **/quo** is equivalent to **/quoteallnames**.</span></span> <span data-ttu-id="3de89-218">指定参数的选项既可以用冒号 (:) 也可以用等号 (=) 作为选项和参数之间的分隔符。</span><span class="sxs-lookup"><span data-stu-id="3de89-218">Options that specify arguments accept either a colon (:) or an equal sign (=) as the separator between the option and the argument.</span></span> <span data-ttu-id="3de89-219">例如，/output: filename 等效于 /output= filename。</span><span class="sxs-lookup"><span data-stu-id="3de89-219">For example, **/output:** *filename* is equivalent to **/output=** *filename*.</span></span>

## <a name="remarks"></a><span data-ttu-id="3de89-220">备注</span><span class="sxs-lookup"><span data-stu-id="3de89-220">Remarks</span></span>

<span data-ttu-id="3de89-221">Ildasm.exe 只对磁盘上的 PE 文件进行操作。</span><span class="sxs-lookup"><span data-stu-id="3de89-221">*Ildasm.exe* only operates on PE files on disk.</span></span> <span data-ttu-id="3de89-222">它不对安装在全局程序集缓存中的文件进行操作。</span><span class="sxs-lookup"><span data-stu-id="3de89-222">It does not operate on files installed in the global assembly cache.</span></span>

<span data-ttu-id="3de89-223">Ildasm.exe 生成的文本文件可以用作 IL 汇编程序 (Ilasm.exe) 的输入。</span><span class="sxs-lookup"><span data-stu-id="3de89-223">The text file produced by *Ildasm.exe* can be used as input to the IL Assembler (*Ilasm.exe*).</span></span> <span data-ttu-id="3de89-224">这很有用，例如在编译用并非支持所有运行时元数据特性的编程语言编写的代码时。</span><span class="sxs-lookup"><span data-stu-id="3de89-224">This is useful, for example, when compiling code in a programming language that does not support all the runtime metadata attributes.</span></span> <span data-ttu-id="3de89-225">通过 Ildasm.exe 编译代码并运行其输出后，可以手动编辑生成的 IL 文本文件以添加缺少的属性。</span><span class="sxs-lookup"><span data-stu-id="3de89-225">After compiling the code and running its output through *Ildasm.exe*, the resulting IL text file can be hand-edited to add the missing attributes.</span></span> <span data-ttu-id="3de89-226">然后可以通过 IL 汇编程序运行此文本文件以生成最终可执行文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-226">You can then run this text file through the IL Assembler to produce a final executable file.</span></span>

> [!NOTE]
> <span data-ttu-id="3de89-227">目前，无法对包含嵌入的本机代码的 PE 文件（例如，由 Visual C++ 生成的 PE 文件）使用此技术。</span><span class="sxs-lookup"><span data-stu-id="3de89-227">Currently, you cannot use this technique with PE files that contain embedded native code (for example, PE files produced by Visual C++).</span></span>  

<span data-ttu-id="3de89-228">你可以使用 IL 反汇编程序中的默认 GUI 在分层树视图中查看任何现有 PE 文件的元数据和反汇编代码。</span><span class="sxs-lookup"><span data-stu-id="3de89-228">You can use the default GUI in the IL Disassembler to view the metadata and disassembled code of any existing PE file in a hierarchical tree view.</span></span> <span data-ttu-id="3de89-229">若要使用此 GUI，请在命令行中键入 ildasm，无需提供 PEfilename 参数或任何选项。</span><span class="sxs-lookup"><span data-stu-id="3de89-229">To use the GUI, type **ildasm** at the command line without supplying the *PEfilename* argument or any options.</span></span> <span data-ttu-id="3de89-230">可从“文件”菜单导航到要加载到 Ildasm.exe 中的 PE 文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-230">From the **File** menu, you can navigate to the PE file that you want to load into *Ildasm.exe*.</span></span> <span data-ttu-id="3de89-231">若要保存为选定 PE 显示的元数据和反汇编代码，请从“文件”菜单中选择“转储”命令。</span><span class="sxs-lookup"><span data-stu-id="3de89-231">To save the metadata and disassembled code displayed for the selected PE, select the **Dump** command from the **File** menu.</span></span> <span data-ttu-id="3de89-232">若要仅保存分层树视图，请从“文件”菜单中选择“转储树视图”命令。</span><span class="sxs-lookup"><span data-stu-id="3de89-232">To save the hierarchical tree view only, select the **Dump Treeview** command from the **File** menu.</span></span> <span data-ttu-id="3de89-233">有关将文件加载到 Ildasm.exe 中和解释输出的详细指南，请参见 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] 附带的 Samples 文件夹中的 Ildasm.exe 教程。</span><span class="sxs-lookup"><span data-stu-id="3de89-233">For a detailed guide to loading a file into *Ildasm.exe* and interpreting the output, see the *Ildasm.exe* Tutorial, located in the Samples folder that ships with the [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)].</span></span>

<span data-ttu-id="3de89-234">如果为 Ildasm.exe 提供一个包含嵌入资源的 PEfilename 参数，则此工具生成多个输出文件：一个包含 IL 代码的文本文件，以及与每个嵌入的托管资源对应的 .resources 文件（使用该资源在元数据中的名称生成）。</span><span class="sxs-lookup"><span data-stu-id="3de89-234">If you provide *Ildasm.exe* with a *PEfilename* argument that contains embedded resources, the tool produces multiple output files: a text file that contains IL code and, for each embedded managed resource, a .resources file produced using the resource's name from metadata.</span></span> <span data-ttu-id="3de89-235">如果 PEfilename 中嵌入了非托管资源，则通过 /output 选项使用 IL 输出指定的文件名生成 .res 文件。</span><span class="sxs-lookup"><span data-stu-id="3de89-235">If an unmanaged resource is embedded in *PEfilename*, a .res file is produced using the filename specified for IL output by the **/output** option.</span></span>

> [!NOTE]
> <span data-ttu-id="3de89-236">Ildasm.exe 仅显示 .obj 和 .lib 输入文件的元数据说明。</span><span class="sxs-lookup"><span data-stu-id="3de89-236">*Ildasm.exe* shows only metadata descriptions for *.obj* and *.lib* input files.</span></span> <span data-ttu-id="3de89-237">不反汇编这些文件类型的 IL 代码。</span><span class="sxs-lookup"><span data-stu-id="3de89-237">IL code for these file types is not disassembled.</span></span>

<span data-ttu-id="3de89-238">可对 .exe 或 .dll 文件运行 Ildasm.exe 来确定该文件是否是托管的。</span><span class="sxs-lookup"><span data-stu-id="3de89-238">You can run *Ildasm.exe* over an.exe or *.dll* file to determine whether the file is managed.</span></span> <span data-ttu-id="3de89-239">如果该文件不是托管的，则此工具将显示一条信息，说明该文件没有有效的公共语言运行时标头，并且无法反汇编。</span><span class="sxs-lookup"><span data-stu-id="3de89-239">If the file is not managed, the tool displays a message stating that the file has no valid common language runtime header and cannot be disassembled.</span></span> <span data-ttu-id="3de89-240">如果该文件是托管的，则此工具将成功运行。</span><span class="sxs-lookup"><span data-stu-id="3de89-240">If the file is managed, the tool runs successfully.</span></span>

## <a name="version-information"></a><span data-ttu-id="3de89-241">版本信息</span><span class="sxs-lookup"><span data-stu-id="3de89-241">Version Information</span></span>

<span data-ttu-id="3de89-242">从 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 开始，Ildasm.exe 将通过显示原始二进制内容来处理无法识别的封送 BLOB（二进制大型对象）。</span><span class="sxs-lookup"><span data-stu-id="3de89-242">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], *Ildasm.exe* handles an unrecognized marshal BLOB (binary large object) by displaying the raw binary content.</span></span> <span data-ttu-id="3de89-243">例如，下面的代码演示 C# 程序生成的封送 BLOB 如何显示：</span><span class="sxs-lookup"><span data-stu-id="3de89-243">For example, the following code shows how a marshal BLOB generated by a C# program is displayed:</span></span>

```csharp
public void Test([MarshalAs((short)70)] int test) { }
```

```
// IL from Ildasm.exe output
.method public hidebysig instance void Test(int32  marshal({ 46 }) test) cil managed
```

<span data-ttu-id="3de89-244">从 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 开始，Ildasm.exe 将显示应用于接口实现的属性，如下方 Ildasm.exe 输出摘录所示：</span><span class="sxs-lookup"><span data-stu-id="3de89-244">Starting with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], *Ildasm.exe* displays attributes that are applied to interface implementations, as shown in the following excerpt from *Ildasm.exe* output:</span></span>

```
.class public auto ansi beforefieldinit MyClass
  extends [mscorlib]System.Object
  implements IMyInterface
  {
    .interfaceimpl type IMyInterface
    .custom instance void
      [mscorlib]System.Diagnostics.DebuggerNonUserCodeAttribute::.ctor() = ( 01 00 00 00 )
      …
```

## <a name="examples"></a><span data-ttu-id="3de89-245">示例</span><span class="sxs-lookup"><span data-stu-id="3de89-245">Examples</span></span>

<span data-ttu-id="3de89-246">下面的命令使 PE 文件 `MyHello.exe` 的元数据和反汇编代码显示在 Ildasm.exe 的默认 GUI 中。</span><span class="sxs-lookup"><span data-stu-id="3de89-246">The following command causes the metadata and disassembled code for the PE file `MyHello.exe` to display in the *Ildasm.exe* default GUI.</span></span>

```console
ildasm myHello.exe
```

<span data-ttu-id="3de89-247">下面的命令对 `MyFile.exe` 文件进行反汇编，并将生成的 IL 汇编程序文本存储在 MyFile.il 文件中。</span><span class="sxs-lookup"><span data-stu-id="3de89-247">The following command disassembles the file `MyFile.exe` and stores the resulting IL Assembler text in the file *MyFile.il*.</span></span>

```console
ildasm MyFile.exe /output:MyFile.il
```

<span data-ttu-id="3de89-248">下面的命令对 `MyFile.exe` 文件进行反汇编，并将结果 IL 汇编程序文本显示到控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="3de89-248">The following command disassembles the file `MyFile.exe` and displays the resulting IL Assembler text to the console window.</span></span>

```console
ildasm MyFile.exe /text
```

<span data-ttu-id="3de89-249">如果文件 `MyApp.exe` 包含嵌入的托管和非托管资源，则下面的命令将生成 4 个文件：MyApp.il、MyApp.res、Icons.resources 和 Message.resources：</span><span class="sxs-lookup"><span data-stu-id="3de89-249">If the file `MyApp.exe` contains embedded managed and unmanaged resources, the following command produces four files: *MyApp.il*, *MyApp.res*, *Icons.resources*, and *Message.resources*:</span></span>

```console
ildasm MyApp.exe /output:MyApp.il
```

<span data-ttu-id="3de89-250">下面的命令对 `MyFile.exe` 的 `MyClass` 类中的 `MyMethod` 方法进行反汇编，并将输出显示到控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="3de89-250">The following command disassembles the method `MyMethod` within the class `MyClass` in `MyFile.exe` and displays the output to the console window.</span></span>

```console
ildasm /item:MyClass::MyMethod MyFile.exe /text
```

<span data-ttu-id="3de89-251">在上面的示例中，可能有几个具有不同签名的名为 `MyMethod` 的方法。</span><span class="sxs-lookup"><span data-stu-id="3de89-251">In the previous example, there could be several methods named `MyMethod` with different signatures.</span></span> <span data-ttu-id="3de89-252">下面的命令对返回类型为 void 且参数类型为 int32 和 string 的 `MyMethod` 实例方法进行反汇编。</span><span class="sxs-lookup"><span data-stu-id="3de89-252">The following command disassembles the instance method `MyMethod` with the return type of **void** and the parameter types **int32** and **string**.</span></span>

```console
ildasm /item:"MyClass::MyMethod(instance void(int32,string)" MyFile.exe /text
```

> [!NOTE]
> <span data-ttu-id="3de89-253">在 .NET Framework 1.0 和 1.1 版中，方法名称之后的左括号必须在签名后面匹配一个右括号：`MyMethod(instance void(int32))`。</span><span class="sxs-lookup"><span data-stu-id="3de89-253">In the .NET Framework versions 1.0 and 1.1, the left parenthesis that follows the method name must be balanced by a right parenthesis after the signature: `MyMethod(instance void(int32))`.</span></span> <span data-ttu-id="3de89-254">从 .NET Framework 2.0 开始，必须省略右括号：(`MyMethod(instance void(int32)`。</span><span class="sxs-lookup"><span data-stu-id="3de89-254">Starting with the .NET Framework 2.0 the closing parenthesis must be omitted: `MyMethod(instance void(int32)`.</span></span>

<span data-ttu-id="3de89-255">若要检索 `static` 方法（在 Visual Basic 中为 `Shared` 方法），则省略关键字 `instance`。</span><span class="sxs-lookup"><span data-stu-id="3de89-255">To retrieve a `static` method (`Shared` method in Visual Basic), omit the keyword `instance`.</span></span> <span data-ttu-id="3de89-256">不属于基元类型（例如 `int32` 和 `string`）的类类型必须包括命名空间并且必须在前面加上关键字 `class`。</span><span class="sxs-lookup"><span data-stu-id="3de89-256">Class types that are not primitive types like `int32` and `string` must include the namespace and must be preceded by the keyword `class`.</span></span> <span data-ttu-id="3de89-257">外部类型的前面必须是用方括号括起来的库名称。</span><span class="sxs-lookup"><span data-stu-id="3de89-257">External types must be preceded by the library name in square brackets.</span></span> <span data-ttu-id="3de89-258">下面的命令对名为 `MyMethod` 的静态方法进行反汇编，该方法具有一个 <xref:System.AppDomain> 类型的参数且其返回类型为 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="3de89-258">The following command disassembles a static method named `MyMethod` that has one parameter of type <xref:System.AppDomain> and has a return type of <xref:System.AppDomain>.</span></span>

```console
ildasm /item:"MyClass::MyMethod(class [mscorlib]System.AppDomain(class [mscorlib]System.AppDomain)" MyFile.exe /text
```

<span data-ttu-id="3de89-259">嵌套类型的前面必须是包含它的类，并用正斜杠进行分隔。</span><span class="sxs-lookup"><span data-stu-id="3de89-259">A nested type must be preceded by its containing class, delimited by a forward slash.</span></span> <span data-ttu-id="3de89-260">例如，如果 `MyNamespace.MyClass` 类包含名为 `NestedClass` 的嵌套类，则按如下方式标识该嵌套类：`class MyNamespace.MyClass/NestedClass`。</span><span class="sxs-lookup"><span data-stu-id="3de89-260">For example, if the `MyNamespace.MyClass` class contains a nested class named `NestedClass`, the nested class is identified as follows: `class MyNamespace.MyClass/NestedClass`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3de89-261">请参阅</span><span class="sxs-lookup"><span data-stu-id="3de89-261">See also</span></span>

[<span data-ttu-id="3de89-262">工具</span><span class="sxs-lookup"><span data-stu-id="3de89-262">Tools</span></span>](../../../docs/framework/tools/index.md)  
[<span data-ttu-id="3de89-263">Ilasm.exe（IL 汇编程序）</span><span class="sxs-lookup"><span data-stu-id="3de89-263">Ilasm.exe (IL Assembler)</span></span>](../../../docs/framework/tools/ilasm-exe-il-assembler.md)  
[<span data-ttu-id="3de89-264">托管执行过程</span><span class="sxs-lookup"><span data-stu-id="3de89-264">Managed Execution Process</span></span>](../../../docs/standard/managed-execution-process.md)  
[<span data-ttu-id="3de89-265">命令提示</span><span class="sxs-lookup"><span data-stu-id="3de89-265">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
