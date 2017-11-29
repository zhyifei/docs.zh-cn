---
title: "代码格式设置准则 (F#)"
description: "F # 编程语言中的以提高可读性，美感、 标准化，并编译了解代码缩进格式设置准则。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3f79717c-f84e-448d-9ce4-90e40a644ba1
ms.openlocfilehash: cc56c67f356b99defd8dc28770f87be1f58443c5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="code-formatting-guidelines"></a><span data-ttu-id="0885b-104">代码格式设置准则</span><span class="sxs-lookup"><span data-stu-id="0885b-104">Code Formatting Guidelines</span></span>

<span data-ttu-id="0885b-105">本主题概述 F # 代码缩进指南。</span><span class="sxs-lookup"><span data-stu-id="0885b-105">This topic summarizes code indentation guidelines for F#.</span></span> <span data-ttu-id="0885b-106">因为 F # 语言的换行符和缩进影响，不是只需可读性问题、 美观问题或编码的标准化问题以正确格式，你的代码。</span><span class="sxs-lookup"><span data-stu-id="0885b-106">Because the F# language is sensitive to line breaks and indentation, it is not just a readability issue, aesthetic issue, or coding standardization issue to format your code correctly.</span></span> <span data-ttu-id="0885b-107">你必须设置正确为其正确编译代码的格式。</span><span class="sxs-lookup"><span data-stu-id="0885b-107">You must format your code correctly for it to compile correctly.</span></span>


## <a name="general-rules-for-indentation"></a><span data-ttu-id="0885b-108">缩进的一般规则</span><span class="sxs-lookup"><span data-stu-id="0885b-108">General Rules for Indentation</span></span>
<span data-ttu-id="0885b-109">需要缩进时，你必须使用空间，不是制表符。</span><span class="sxs-lookup"><span data-stu-id="0885b-109">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="0885b-110">需要至少一个空格。</span><span class="sxs-lookup"><span data-stu-id="0885b-110">At least one space is required.</span></span> <span data-ttu-id="0885b-111">您的组织可以创建编码标准来指定要用于缩进; 的空格数典型的缩进的出现位置的每个级别的缩进的三个或四个空格。</span><span class="sxs-lookup"><span data-stu-id="0885b-111">Your organization can create coding standards to specify the number of spaces to use for indentation; three or four spaces of indentation at each level where indentation occurs is typical.</span></span> <span data-ttu-id="0885b-112">你可以配置 Visual Studio 以通过更改中的选项根据你的组织的缩进标准`Options`对话框中，可从`Tools`菜单。</span><span class="sxs-lookup"><span data-stu-id="0885b-112">You can configure Visual Studio to match your organization's indentation standards by changing the options in the `Options` dialog box, which is available from the `Tools` menu.</span></span> <span data-ttu-id="0885b-113">在`Text Editor`节点，展开`F#`，然后单击`Tabs`。</span><span class="sxs-lookup"><span data-stu-id="0885b-113">In the `Text Editor` node, expand `F#` and then click `Tabs`.</span></span> <span data-ttu-id="0885b-114">有关可用选项的说明，请参阅[选项、 文本编辑器、 所有语言、 选项卡](https://msdn.microsoft.com/library/7sffa753.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0885b-114">For a description of the available options, see [Options, Text Editor, All Languages, Tabs](https://msdn.microsoft.com/library/7sffa753.aspx).</span></span>

<span data-ttu-id="0885b-115">一般情况下，当编译器分析你的代码，这样可保持内部堆栈，该值指示当前的嵌套级别。</span><span class="sxs-lookup"><span data-stu-id="0885b-115">In general, when the compiler parses your code, it maintains an internal stack that indicates the current level of nesting.</span></span> <span data-ttu-id="0885b-116">当代码缩进时，一个新的嵌套级别创建，或推送到此内部堆栈上。</span><span class="sxs-lookup"><span data-stu-id="0885b-116">When code is indented, a new level of nesting is created, or pushed onto this internal stack.</span></span> <span data-ttu-id="0885b-117">一种构造结束时，将弹出级别。</span><span class="sxs-lookup"><span data-stu-id="0885b-117">When a construct ends, the level is popped.</span></span> <span data-ttu-id="0885b-118">缩进是一种方法来指示级别的末尾，并弹出内部堆栈的方式，但某些令牌还会导致级别弹出，如`end`关键字，或者右大括号或右括号。</span><span class="sxs-lookup"><span data-stu-id="0885b-118">Indentation is one way to signal the end of a level and pop the internal stack, but certain tokens also cause the level to be popped, such as the `end` keyword, or a closing brace or parenthesis.</span></span>

<span data-ttu-id="0885b-119">多行的构造，如类型定义中中的代码的函数定义`try...with`构造，和循环构造，必须是相对于缩进的构造的开始行。</span><span class="sxs-lookup"><span data-stu-id="0885b-119">Code in a multiline construct, such as a type definition, function definition, `try...with` construct, and looping constructs, must be indented relative to the opening line of the construct.</span></span> <span data-ttu-id="0885b-120">首行缩进建立同一构造中的后续代码的列位置。</span><span class="sxs-lookup"><span data-stu-id="0885b-120">The first indented line establishes a column position for subsequent code in the same construct.</span></span> <span data-ttu-id="0885b-121">缩进级别称为*上下文*。</span><span class="sxs-lookup"><span data-stu-id="0885b-121">The indentation level is called a *context*.</span></span> <span data-ttu-id="0885b-122">中的列位置设置最小列中，称为*越位线*，后面是相同的上下文中的代码行。</span><span class="sxs-lookup"><span data-stu-id="0885b-122">The column position sets a minimum column, referred to as an *offside line*, for subsequent lines of code that are in the same context.</span></span> <span data-ttu-id="0885b-123">遇到的代码行时即比此建立的列位置的更少缩进，编译器假定上下文已结束，并且，你在现在编码在下一步的级别，在以前的上下文中。</span><span class="sxs-lookup"><span data-stu-id="0885b-123">When a line of code is encountered that is indented less than this established column position, the compiler assumes that the context has ended and that you are now coding at the next level up, in the previous context.</span></span> <span data-ttu-id="0885b-124">术语*越位*用于描述在其中的代码行触发构造结束，因为它不会缩进程度的条件。</span><span class="sxs-lookup"><span data-stu-id="0885b-124">The term *offside* is used to describe the condition in which a line of code triggers the end of a construct because it is not indented far enough.</span></span> <span data-ttu-id="0885b-125">换而言之，越位线左侧的代码处于越位位置。</span><span class="sxs-lookup"><span data-stu-id="0885b-125">In other words, code to the left of an offside line is offside.</span></span> <span data-ttu-id="0885b-126">在正确缩进代码中，你利用越位规则以描绘构造的末尾。</span><span class="sxs-lookup"><span data-stu-id="0885b-126">In correctly indented code, you take advantage of the offside rule in order to delineate the end of constructs.</span></span> <span data-ttu-id="0885b-127">如果使用了不正确的缩进，则越位情况可能会导致编译器发出警告，或可能导致你的代码的不正确解释。</span><span class="sxs-lookup"><span data-stu-id="0885b-127">If you use indentation improperly, an offside condition can cause the compiler to issue a warning or can lead to the incorrect interpretation of your code.</span></span>

<span data-ttu-id="0885b-128">越位线确定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="0885b-128">Offside lines are determined as follows.</span></span>


- <span data-ttu-id="0885b-129">`=`与关联的令牌`let`引入越位线之后的第一个标记列`=`登录。</span><span class="sxs-lookup"><span data-stu-id="0885b-129">An `=` token associated with a `let` introduces an offside line at the column of the first token after the `=` sign.</span></span>


- <span data-ttu-id="0885b-130">在`if...then...else`表达式，后面的第一个标记的列位置`then`关键字或`else`关键字引入越位线。</span><span class="sxs-lookup"><span data-stu-id="0885b-130">In an `if...then...else` expression, the column position of the first token after the `then` keyword or the `else` keyword introduces an offside line.</span></span>


- <span data-ttu-id="0885b-131">在`try...with`表达式，后面的第一个标记`try`引入越位线。</span><span class="sxs-lookup"><span data-stu-id="0885b-131">In a `try...with` expression, the first token after `try` introduces an offside line.</span></span>


- <span data-ttu-id="0885b-132">在`match`表达式，后面的第一个标记`with`和在每行后的第一个标记`->`引入越位线。</span><span class="sxs-lookup"><span data-stu-id="0885b-132">In a `match` expression, the first token after `with` and the first token after each `->` introduce offside lines.</span></span>


- <span data-ttu-id="0885b-133">后面的第一个标记`with`类型中扩展引入越位线。</span><span class="sxs-lookup"><span data-stu-id="0885b-133">The first token after `with` in a type extension introduces an offside line.</span></span>


- <span data-ttu-id="0885b-134">在左大括号或圆括号，或之后的第一个标记`begin`关键字，引入越位线。</span><span class="sxs-lookup"><span data-stu-id="0885b-134">The first token after an opening brace or parenthesis, or after the `begin` keyword, introduces an offside line.</span></span>


- <span data-ttu-id="0885b-135">在关键字中的第一个字符`let`， `if`，和`module`引入越位线。</span><span class="sxs-lookup"><span data-stu-id="0885b-135">The first character in the keywords `let`, `if`, and `module` introduce offside lines.</span></span>


<span data-ttu-id="0885b-136">下面的代码示例阐释的缩进规则。</span><span class="sxs-lookup"><span data-stu-id="0885b-136">The following code examples illustrate the indentation rules.</span></span> <span data-ttu-id="0885b-137">在这里，print 语句依赖于将其与合适的上下文关联的缩进。</span><span class="sxs-lookup"><span data-stu-id="0885b-137">Here, the print statements rely on indentation to associate them with the appropriate context.</span></span> <span data-ttu-id="0885b-138">每次切换缩进，上下文将弹出，并返回到以前的上下文。</span><span class="sxs-lookup"><span data-stu-id="0885b-138">Every time the indentation shifts, the context is popped and returns to the previous context.</span></span> <span data-ttu-id="0885b-139">因此，在每次迭代; 末尾打印一个空格"已完成 ！"</span><span class="sxs-lookup"><span data-stu-id="0885b-139">Therefore, a space is printed at the end of each iteration; "Done!"</span></span> <span data-ttu-id="0885b-140">只会打印一次，因为越位缩进建立它不是循环的一部分。</span><span class="sxs-lookup"><span data-stu-id="0885b-140">is only printed one time because the offside indentation establishes that it is not part of the loop.</span></span> <span data-ttu-id="0885b-141">打印"顶级上下文"不是字符串的函数的一部分。</span><span class="sxs-lookup"><span data-stu-id="0885b-141">The printing of the string "Top-level context" is not part of the function.</span></span> <span data-ttu-id="0885b-142">因此，它将打印首先，在静态初始化期间调用该函数之前。</span><span class="sxs-lookup"><span data-stu-id="0885b-142">Therefore, it is printed first, during the static initialization, before the function is called.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet1.fs)]

<span data-ttu-id="0885b-143">输出如下所示。</span><span class="sxs-lookup"><span data-stu-id="0885b-143">The output is as follows.</span></span>

```
Top-level context

(Negative number) Zero 1 2 3 Done!
```

<span data-ttu-id="0885b-144">当在中断较长的行时, 必须比封闭构造缩进的行延续。</span><span class="sxs-lookup"><span data-stu-id="0885b-144">When you break long lines, the continuation of the line must be indented farther than the enclosing construct.</span></span> <span data-ttu-id="0885b-145">例如，函数自变量必须缩进比第一个字符的函数名称，如下面的代码中所示。</span><span class="sxs-lookup"><span data-stu-id="0885b-145">For example, function arguments must be indented farther than the first character of the function name, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet2.fs)]

<span data-ttu-id="0885b-146">下一节中所述，有例外这些规则。</span><span class="sxs-lookup"><span data-stu-id="0885b-146">There are exceptions to these rules, as described in the next section.</span></span>


## <a name="indentation-in-modules"></a><span data-ttu-id="0885b-147">模块中的缩进</span><span class="sxs-lookup"><span data-stu-id="0885b-147">Indentation in Modules</span></span>
<span data-ttu-id="0885b-148">本地模块中的代码必须缩进相对于该模块，但顶级模块中的代码不一定要缩进。</span><span class="sxs-lookup"><span data-stu-id="0885b-148">Code in a local module must be indented relative to the module, but code in a top-level module does not have to be indented.</span></span> <span data-ttu-id="0885b-149">Namespace 元素无需进行缩进。</span><span class="sxs-lookup"><span data-stu-id="0885b-149">Namespace elements do not have to be indented.</span></span>

<span data-ttu-id="0885b-150">下面的代码示例说明这一点。</span><span class="sxs-lookup"><span data-stu-id="0885b-150">The following code examples illustrate this.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet3.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet4.fs)]

<span data-ttu-id="0885b-151">有关详细信息，请参阅[模块](modules.md)。</span><span class="sxs-lookup"><span data-stu-id="0885b-151">For more information, see [Modules](modules.md).</span></span>


## <a name="exceptions-to-the-basic-indentation-rules"></a><span data-ttu-id="0885b-152">基本的缩进规则的例外</span><span class="sxs-lookup"><span data-stu-id="0885b-152">Exceptions to the Basic Indentation Rules</span></span>
<span data-ttu-id="0885b-153">一般规则上, 一节中所述是多行构造中的代码，必须相对于构造的第一行的缩进缩进和第一个越位线发生时由确定构造的末尾。</span><span class="sxs-lookup"><span data-stu-id="0885b-153">The general rule, as described in the previous section, is that code in multiline constructs must be indented relative to the indentation of the first line of the construct, and that the end of the construct is determined by when the first offside line occurs.</span></span> <span data-ttu-id="0885b-154">有关上下文结束时，某些构造，如规则的例外`try...with`表达式，`if...then...else`表达式，以及如何使用`and`语法来声明相互递归函数或类型，具有多个部分。</span><span class="sxs-lookup"><span data-stu-id="0885b-154">An exception to the rule about when contexts end is that some constructs, such as the `try...with` expression, the `if...then...else` expression, and the use of `and` syntax for declaring mutually recursive functions or types, have multiple parts.</span></span> <span data-ttu-id="0885b-155">如后面的部分中，缩进`then`和`else`中`if...then...else`表达式，在同一级别作为令牌与表达式开头，而不是，该值指示结束到上下文，它表示相同的上下文的下一部分。</span><span class="sxs-lookup"><span data-stu-id="0885b-155">You indent the later parts, such as `then` and `else` in an `if...then...else` expression, at the same level as the token that starts the expression, but instead of indicating an end to the context, it represents the next part of the same context.</span></span> <span data-ttu-id="0885b-156">因此，`if...then...else`可以写入表达式，如下面的代码示例所示。</span><span class="sxs-lookup"><span data-stu-id="0885b-156">Therefore, an `if...then...else` expression can be written as in the following code example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet5.fs)]

<span data-ttu-id="0885b-157">越位规则的例外仅适用于`then`和`else`关键字。</span><span class="sxs-lookup"><span data-stu-id="0885b-157">The exception to the offside rule applies only to the `then` and `else` keywords.</span></span> <span data-ttu-id="0885b-158">因此，尽管这不是错误缩进`then`和`else`进一步，失败中的代码行缩进`then`块生成警告。</span><span class="sxs-lookup"><span data-stu-id="0885b-158">Therefore, although it is not an error to indent the `then` and `else` further, failing to indent the lines of code in a `then` block produces a warning.</span></span> <span data-ttu-id="0885b-159">下面的代码行对此进行了阐释。</span><span class="sxs-lookup"><span data-stu-id="0885b-159">This is illustrated in the following lines of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet6.fs)]
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet7.fs)]

<span data-ttu-id="0885b-160">中的代码`else`块，其他特殊规则适用。</span><span class="sxs-lookup"><span data-stu-id="0885b-160">For code in an `else` block, an additional special rule applies.</span></span> <span data-ttu-id="0885b-161">在前面的示例才会出现警告中的代码`then`块中，未对中的代码`else`块。</span><span class="sxs-lookup"><span data-stu-id="0885b-161">The warning in the previous example occurs only on the code in the `then` block, not on the code in the `else` block.</span></span> <span data-ttu-id="0885b-162">这使您可以编写一个函数开头的各种情况检查而不进行强制函数，这可能是中的代码的其余部分的代码`else`块，缩进。</span><span class="sxs-lookup"><span data-stu-id="0885b-162">This allows you to write code that checks for various conditions at the beginning of a function without forcing the rest of the code for the function, which might be in an `else` block, to be indented.</span></span> <span data-ttu-id="0885b-163">因此，你可以编写以下代码而不会生成一个警告。</span><span class="sxs-lookup"><span data-stu-id="0885b-163">Thus, you can write the following without producing a warning.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet8.fs)]

<span data-ttu-id="0885b-164">另一种例外上下文结束时行缩进距离与上一行是对于中缀运算符，如规则`+`和`|>`。</span><span class="sxs-lookup"><span data-stu-id="0885b-164">Another exception to the rule that contexts end when a line is not indented as far as a previous line is for infix operators, such as `+` and `|>`.</span></span> <span data-ttu-id="0885b-165">允许以中缀运算符开头的行开始`(1 + oplength)`列而不会触发上下文，结束的正常位置之前其中`oplength`构成运算符的字符数。</span><span class="sxs-lookup"><span data-stu-id="0885b-165">Lines that start with infix operators are permitted to begin `(1 + oplength)` columns before the normal position without triggering an end to the context, where `oplength` is the number of characters that make up the operator.</span></span> <span data-ttu-id="0885b-166">这将导致触发 after 运算符，确保它与上一行的第一个标记。</span><span class="sxs-lookup"><span data-stu-id="0885b-166">This causes the first token after the operator to align with the previous line.</span></span>

<span data-ttu-id="0885b-167">例如，在下面的代码中，`+`允许符号是小于上一行的缩进的两个列。</span><span class="sxs-lookup"><span data-stu-id="0885b-167">For example, in the following code, the `+` symbol is permitted to be indented two columns less than the previous line.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet9.fs)]

<span data-ttu-id="0885b-168">尽管随着的嵌套级别变得更高版本，通常会增加缩进，有一些编译器允许你重置为较低的列位置的缩进的下列几种构造。</span><span class="sxs-lookup"><span data-stu-id="0885b-168">Although indentation usually increases as the level of nesting becomes higher, there are several constructs in which the compiler allows you to reset the indentation to a lower column position.</span></span>

<span data-ttu-id="0885b-169">允许重置的列位置的构造如下所示：</span><span class="sxs-lookup"><span data-stu-id="0885b-169">The constructs that permit a reset of column position are as follows:</span></span>


- <span data-ttu-id="0885b-170">匿名函数的主体。</span><span class="sxs-lookup"><span data-stu-id="0885b-170">Bodies of anonymous functions.</span></span> <span data-ttu-id="0885b-171">在下面的代码中，打印的表达式在远离比左侧列位置开始`fun`关键字。</span><span class="sxs-lookup"><span data-stu-id="0885b-171">In the following code, the print expression starts at a column position that is farther to the left than the `fun` keyword.</span></span> <span data-ttu-id="0885b-172">但是，行必须启动在开始之前的缩进级别的左边的列 (即，左侧`L`中`List`)。</span><span class="sxs-lookup"><span data-stu-id="0885b-172">However, the line must not start at a column to the left of the start of the previous indentation level (that is, to the left of the `L` in `List`).</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet10.fs)]

- <span data-ttu-id="0885b-173">构造括在圆括号或通过`begin`和`end`中`then`或`else`块`if...then...else`表达式，提供缩进是不小于的列位置`if`关键字。</span><span class="sxs-lookup"><span data-stu-id="0885b-173">Constructs enclosed by parentheses or by `begin` and `end` in a `then` or `else` block of an `if...then...else` expression, provided the indentation is no less than the column position of the `if` keyword.</span></span> <span data-ttu-id="0885b-174">此异常使得在其中的编码样式左括号或`begin`后的行的末尾使用`then`或`else`。</span><span class="sxs-lookup"><span data-stu-id="0885b-174">This exception allows for a coding style in which an opening parenthesis or `begin` is used at the end of a line after `then` or `else`.</span></span>


- <span data-ttu-id="0885b-175">主体的模块、 类、 接口和结构由分隔`begin...end`， `{...}`， `class...end`，或`interface...end`。</span><span class="sxs-lookup"><span data-stu-id="0885b-175">Bodies of modules, classes, interfaces, and structures delimited by `begin...end`, `{...}`, `class...end`, or `interface...end`.</span></span> <span data-ttu-id="0885b-176">这样可在其中打开关键字类型定义的类型名称与同一行而不进行强制整个正文要比期初关键字缩进样式。</span><span class="sxs-lookup"><span data-stu-id="0885b-176">This allows for a style in which the opening keyword of a type definition can be on the same line as the type name without forcing the whole body to be indented farther than the opening keyword.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/code-formatting/snippet13.fs)]


## <a name="see-also"></a><span data-ttu-id="0885b-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0885b-177">See Also</span></span>
[<span data-ttu-id="0885b-178">F# 语言参考</span><span class="sxs-lookup"><span data-stu-id="0885b-178">F# Language Reference</span></span>](index.md)
