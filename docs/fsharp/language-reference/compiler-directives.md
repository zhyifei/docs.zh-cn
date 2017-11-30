---
title: "编译器指令 (F#)"
description: "了解有关 F # 语言预处理器指令、 条件编译指令、 行指令和编译器指令。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 93aef07a-6747-4ce4-a10f-a05168978af6
ms.openlocfilehash: b4305d24163f9b23631d5efb6e838f55127cd9f5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="compiler-directives"></a><span data-ttu-id="242dd-104">编译器指令</span><span class="sxs-lookup"><span data-stu-id="242dd-104">Compiler Directives</span></span>

<span data-ttu-id="242dd-105">本主题介绍处理器指令和编译器指令。</span><span class="sxs-lookup"><span data-stu-id="242dd-105">This topic describes processor directives and compiler directives.</span></span>


## <a name="preprocessor-directives"></a><span data-ttu-id="242dd-106">预处理器指令</span><span class="sxs-lookup"><span data-stu-id="242dd-106">Preprocessor Directives</span></span>
<span data-ttu-id="242dd-107">预处理器指令以 # 符号作为前缀，出现在行本身上。</span><span class="sxs-lookup"><span data-stu-id="242dd-107">A preprocessor directive is prefixed with the # symbol and appears on a line by itself.</span></span> <span data-ttu-id="242dd-108">它由预处理器进行解释，后者在编译器本身之前运行。</span><span class="sxs-lookup"><span data-stu-id="242dd-108">It is interpreted by the preprocessor, which runs before the compiler itself.</span></span>

<span data-ttu-id="242dd-109">下表列出了 F# 中可用的预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="242dd-109">The following table lists the preprocessor directives that are available in F#.</span></span>


|<span data-ttu-id="242dd-110">指令</span><span class="sxs-lookup"><span data-stu-id="242dd-110">Directive</span></span>|<span data-ttu-id="242dd-111">描述</span><span class="sxs-lookup"><span data-stu-id="242dd-111">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="242dd-112">`#if`*符号*</span><span class="sxs-lookup"><span data-stu-id="242dd-112">`#if` *symbol*</span></span>|<span data-ttu-id="242dd-113">支持条件编译。</span><span class="sxs-lookup"><span data-stu-id="242dd-113">Supports conditional compilation.</span></span> <span data-ttu-id="242dd-114">后面部分中的代码`#if`则会包括*符号*定义。</span><span class="sxs-lookup"><span data-stu-id="242dd-114">Code in the section after the `#if` is included if the *symbol* is defined.</span></span>|
|`#else`|<span data-ttu-id="242dd-115">支持条件编译。</span><span class="sxs-lookup"><span data-stu-id="242dd-115">Supports conditional compilation.</span></span> <span data-ttu-id="242dd-116">如果未定义与前面的 `#if` 一起使用的符号，则将一段代码标记为包含在内。</span><span class="sxs-lookup"><span data-stu-id="242dd-116">Marks a section of code to include if the symbol used with the previous `#if` is not defined.</span></span>|
|`#endif`|<span data-ttu-id="242dd-117">支持条件编译。</span><span class="sxs-lookup"><span data-stu-id="242dd-117">Supports conditional compilation.</span></span> <span data-ttu-id="242dd-118">标记条件代码段的末尾。</span><span class="sxs-lookup"><span data-stu-id="242dd-118">Marks the end of a conditional section of code.</span></span>|
|<span data-ttu-id="242dd-119">`#`[行]*int*，</span><span class="sxs-lookup"><span data-stu-id="242dd-119">`#`[line] *int*,</span></span><br/><span data-ttu-id="242dd-120">`#`[行]*int* *字符串*，</span><span class="sxs-lookup"><span data-stu-id="242dd-120">`#`[line] *int* *string*,</span></span><br/><span data-ttu-id="242dd-121">`#`[行]*int* *原义字符串*</span><span class="sxs-lookup"><span data-stu-id="242dd-121">`#`[line] *int* *verbatim-string*</span></span>|<span data-ttu-id="242dd-122">指示原始源代码行和文件名以用于调试。</span><span class="sxs-lookup"><span data-stu-id="242dd-122">Indicates the original source code line and file name, for debugging.</span></span> <span data-ttu-id="242dd-123">此功能是为生成 F# 源代码的工具而提供的。</span><span class="sxs-lookup"><span data-stu-id="242dd-123">This feature is provided for tools that generate F# source code.</span></span>|
|<span data-ttu-id="242dd-124">`#nowarn`*warningcode*</span><span class="sxs-lookup"><span data-stu-id="242dd-124">`#nowarn` *warningcode*</span></span>|<span data-ttu-id="242dd-125">禁用编译器警告。</span><span class="sxs-lookup"><span data-stu-id="242dd-125">Disables a compiler warning or warnings.</span></span> <span data-ttu-id="242dd-126">若要禁用警告，请在编译器输出中查找其编号，然后将它包含在引号内。</span><span class="sxs-lookup"><span data-stu-id="242dd-126">To disable a warning, find its number from the compiler output and include it in quotation marks.</span></span> <span data-ttu-id="242dd-127">省略“FS”前缀。</span><span class="sxs-lookup"><span data-stu-id="242dd-127">Omit the "FS" prefix.</span></span> <span data-ttu-id="242dd-128">若要禁用同一行上的多个警告编号，请将每个编号用引号引起来，并使用空格分隔每个字符串。</span><span class="sxs-lookup"><span data-stu-id="242dd-128">To disable multiple warning numbers on the same line, include each number in quotation marks, and separate each string by a space.</span></span> <span data-ttu-id="242dd-129">例如: </span><span class="sxs-lookup"><span data-stu-id="242dd-129">For example:</span></span>

`#nowarn "9" "40"`


<span data-ttu-id="242dd-130">禁用警告的效果应用于整个文件，包括对文件的部分位于该指令之前。 |</span><span class="sxs-lookup"><span data-stu-id="242dd-130">The effect of disabling a warning applies to the entire file, including portions of the file that precede the directive.|</span></span>

## <a name="conditional-compilation-directives"></a><span data-ttu-id="242dd-131">条件编译指令</span><span class="sxs-lookup"><span data-stu-id="242dd-131">Conditional Compilation Directives</span></span>
<span data-ttu-id="242dd-132">由这些指令之一停用的代码显示为灰色 Visual StudioCode 编辑器中。</span><span class="sxs-lookup"><span data-stu-id="242dd-132">Code that is deactivated by one of these directives appears dimmed in the Visual StudioCode Editor.</span></span>


>[!NOTE] 
<span data-ttu-id="242dd-133">条件编译指令的行为与它在其他语言中的行为不同。</span><span class="sxs-lookup"><span data-stu-id="242dd-133">The behavior of the conditional compilation directives is not the same as it is in other languages.</span></span> <span data-ttu-id="242dd-134">例如，不能使用涉及符号的布尔表达式，并且 `true` 和 `false` 没有特殊含义。</span><span class="sxs-lookup"><span data-stu-id="242dd-134">For example, you cannot use Boolean expressions involving symbols, and `true` and `false` have no special meaning.</span></span> <span data-ttu-id="242dd-135">在 `if` 指令中使用的符号必须通过命令行或在项目设置中定义；没有 `define` 预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="242dd-135">Symbols that you use in the `if` directive must be defined by the command line or in the project settings; there is no `define` preprocessor directive.</span></span>


<span data-ttu-id="242dd-136">以下代码演示了 `#if`、`#else` 和 `#endif` 指令的用法。</span><span class="sxs-lookup"><span data-stu-id="242dd-136">The following code illustrates the use of the `#if`, `#else`, and `#endif` directives.</span></span> <span data-ttu-id="242dd-137">在此示例中，代码包含两个版本的 `function1` 定义。</span><span class="sxs-lookup"><span data-stu-id="242dd-137">In this example, the code contains two versions of the definition of `function1`.</span></span> <span data-ttu-id="242dd-138">当`VERSION1`使用定义[-define 编译器选项](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04)，之间的代码`#if`指令和`#else`激活指令。</span><span class="sxs-lookup"><span data-stu-id="242dd-138">When `VERSION1` is defined by using the [-define compiler option](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04), the code between the `#if` directive and the `#else` directive is activated.</span></span> <span data-ttu-id="242dd-139">否则，会激活 `#else` 与 `#endif` 之间的代码。</span><span class="sxs-lookup"><span data-stu-id="242dd-139">Otherwise, the code between `#else` and `#endif` is activated.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

<span data-ttu-id="242dd-140">F# 中没有 `#define` 预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="242dd-140">There is no `#define` preprocessor directive in F#.</span></span> <span data-ttu-id="242dd-141">必须使用编译器选项或项目设置来定义 `#if` 指令使用的符号。</span><span class="sxs-lookup"><span data-stu-id="242dd-141">You must use the compiler option or project settings to define the symbols used by the `#if` directive.</span></span>

<span data-ttu-id="242dd-142">条件编译指令可以进行嵌套。</span><span class="sxs-lookup"><span data-stu-id="242dd-142">Conditional compilation directives can be nested.</span></span> <span data-ttu-id="242dd-143">缩进对于预处理器指令并不重要。</span><span class="sxs-lookup"><span data-stu-id="242dd-143">Indentation is not significant for preprocessor directives.</span></span>


## <a name="line-directives"></a><span data-ttu-id="242dd-144">行指令</span><span class="sxs-lookup"><span data-stu-id="242dd-144">Line Directives</span></span>
<span data-ttu-id="242dd-145">在生成时，编译器会通过引用每个错误发生时所在的行号来报告 F# 代码中的错误。</span><span class="sxs-lookup"><span data-stu-id="242dd-145">When building, the compiler reports errors in F# code by referencing line numbers on which each error occurs.</span></span> <span data-ttu-id="242dd-146">这些行号从 1 开始（表示文件中的第一行）。</span><span class="sxs-lookup"><span data-stu-id="242dd-146">These line numbers start at 1 for the first line in a file.</span></span> <span data-ttu-id="242dd-147">但是，如果要从另一种工具生成 F# 源代码，则生成的代码中的行号通常没什么意义，因为生成的 F# 代码中的错误很可能是由其他来源导致的。</span><span class="sxs-lookup"><span data-stu-id="242dd-147">However, if you are generating F# source code from another tool, the line numbers in the generated code are generally not of interest, because the errors in the generated F# code most likely arise from another source.</span></span> <span data-ttu-id="242dd-148">`#line` 指令提供了一种方法，使生成 F# 源代码的工具的作者可以将有关原始行号和源文件的信息传递给生成的 F# 代码。</span><span class="sxs-lookup"><span data-stu-id="242dd-148">The `#line` directive provides a way for authors of tools that generate F# source code to pass information about the original line numbers and source files to the generated F# code.</span></span>

<span data-ttu-id="242dd-149">使用 `#line` 指令时，必须将文件名括在引号内。</span><span class="sxs-lookup"><span data-stu-id="242dd-149">When you use the `#line` directive, file names must be enclosed in quotation marks.</span></span> <span data-ttu-id="242dd-150">除非原义标记 (`@`) 出现在字符串前面，否则必须使用两个反斜杠字符（而不是一个）对反斜杠字符进行转义，才能在路径中使用它们。</span><span class="sxs-lookup"><span data-stu-id="242dd-150">Unless the verbatim token (`@`) appears in front of the string, you must escape backslash characters by using two backslash characters instead of one in order to use them in the path.</span></span> <span data-ttu-id="242dd-151">以下是有效的行标记。</span><span class="sxs-lookup"><span data-stu-id="242dd-151">The following are valid line tokens.</span></span> <span data-ttu-id="242dd-152">在这些示例中，假设原始文件 `Script1` 会在通过某种工具运行时产生自动生成的 F# 代码文件，并且这些指令的位置处的代码是从文件 `Script1` 中第 25 行处的一些标记生成的。</span><span class="sxs-lookup"><span data-stu-id="242dd-152">In these examples, assume that the original file `Script1` results in an automatically generated F# code file when it is run through a tool, and that the code at the location of these directives is generated from some tokens at line 25 in file `Script1`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

<span data-ttu-id="242dd-153">这些标记指示在此位置生成的 F# 代码派生自位于 `Script1` 中第 `25` 行上或附近的一些构造。</span><span class="sxs-lookup"><span data-stu-id="242dd-153">These tokens indicate that the F# code generated at this location is derived from some constructs at or near line `25` in `Script1`.</span></span>


## <a name="compiler-directives"></a><span data-ttu-id="242dd-154">编译器指令</span><span class="sxs-lookup"><span data-stu-id="242dd-154">Compiler Directives</span></span>
<span data-ttu-id="242dd-155">编译器指令类似于预处理器指令，因为它们以 # 符号作为前缀，但它们留给编译器进行解释和处理，而不是由预处理器进行解释。</span><span class="sxs-lookup"><span data-stu-id="242dd-155">Compiler directives resemble preprocessor directives, because they are prefixed with a # sign, but instead of being interpreted by the preprocessor, they are left for the compiler to interpret and act on.</span></span>

<span data-ttu-id="242dd-156">下表列出了在 F# 中可用的编译器指令。</span><span class="sxs-lookup"><span data-stu-id="242dd-156">The following table lists the compiler directive that is available in F#.</span></span>


|<span data-ttu-id="242dd-157">指令</span><span class="sxs-lookup"><span data-stu-id="242dd-157">Directive</span></span>|<span data-ttu-id="242dd-158">描述</span><span class="sxs-lookup"><span data-stu-id="242dd-158">Description</span></span>|
|---------|-----------|
|<span data-ttu-id="242dd-159">`#light`["on"</span><span class="sxs-lookup"><span data-stu-id="242dd-159">`#light` ["on"</span></span>|<span data-ttu-id="242dd-160">"关闭"]</span><span class="sxs-lookup"><span data-stu-id="242dd-160">"off"]</span></span>|<span data-ttu-id="242dd-161">启用或禁用轻量语法，以便与其他版本的 ML 兼容。</span><span class="sxs-lookup"><span data-stu-id="242dd-161">Enables or disables lightweight syntax, for compatibility with other versions of ML.</span></span> <span data-ttu-id="242dd-162">默认情况下，轻量语法处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="242dd-162">By default, lightweight syntax is enabled.</span></span> <span data-ttu-id="242dd-163">详细语法始终处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="242dd-163">Verbose syntax is always enabled.</span></span> <span data-ttu-id="242dd-164">因此，可以同时使用轻量语法和详细语法。</span><span class="sxs-lookup"><span data-stu-id="242dd-164">Therefore, you can use both lightweight syntax and verbose syntax.</span></span> <span data-ttu-id="242dd-165">指令 `#light` 本身等效于 `#light "on"`。</span><span class="sxs-lookup"><span data-stu-id="242dd-165">The directive `#light` by itself is equivalent to `#light "on"`.</span></span> <span data-ttu-id="242dd-166">如果指定 `#light "off"`，则必须对所有语言构造使用详细语法。</span><span class="sxs-lookup"><span data-stu-id="242dd-166">If you specify `#light "off"`, you must use verbose syntax for all language constructs.</span></span> <span data-ttu-id="242dd-167">F# 文档中展示的语法基于使用轻量语法这一假设。</span><span class="sxs-lookup"><span data-stu-id="242dd-167">Syntax in the documentation for F# is presented with the assumption that you are using lightweight syntax.</span></span> <span data-ttu-id="242dd-168">有关详细信息，请参阅[详细语法](verbose-syntax.md)。</span><span class="sxs-lookup"><span data-stu-id="242dd-168">For more information, see [Verbose Syntax](verbose-syntax.md).</span></span>|
<span data-ttu-id="242dd-169">有关解释器 (fsi.exe) 指令，请参阅[使用 F # 进行交互式编程](../tutorials/fsharp-interactive/index.md)。</span><span class="sxs-lookup"><span data-stu-id="242dd-169">For interpreter (fsi.exe) directives, see [Interactive Programming with F#](../tutorials/fsharp-interactive/index.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="242dd-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="242dd-170">See Also</span></span>
[<span data-ttu-id="242dd-171">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="242dd-171">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="242dd-172">编译器选项</span><span class="sxs-lookup"><span data-stu-id="242dd-172">Compiler Options</span></span>](compiler-options.md)

