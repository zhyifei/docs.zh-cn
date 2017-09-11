---
title: "C# 编码约定（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9f32fdc0eb1954cdac30c39e05c74d43301d850c
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="be05b-102">C# 编码约定（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="be05b-102">C# Coding Conventions (C# Programming Guide)</span></span>
<span data-ttu-id="be05b-103">[C# 语言规范](http://go.microsoft.com/fwlink/?LinkId=199552)未定义编码标准。</span><span class="sxs-lookup"><span data-stu-id="be05b-103">The [C# Language Specification](http://go.microsoft.com/fwlink/?LinkId=199552) does not define a coding standard.</span></span> <span data-ttu-id="be05b-104">但是，Microsoft 根据本主题中的准则来开发样本和文档。</span><span class="sxs-lookup"><span data-stu-id="be05b-104">However, the guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
 <span data-ttu-id="be05b-105">编码约定可实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="be05b-105">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="be05b-106">它们为代码创建一致的外观，以确保读取器专注于内容而非布局。</span><span class="sxs-lookup"><span data-stu-id="be05b-106">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="be05b-107">它们使得读取器可以通过基于之前的经验进行的假设更快地理解代码。</span><span class="sxs-lookup"><span data-stu-id="be05b-107">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="be05b-108">它们便于复制、更改和维护代码。</span><span class="sxs-lookup"><span data-stu-id="be05b-108">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="be05b-109">它们展示 C# 最佳做法。</span><span class="sxs-lookup"><span data-stu-id="be05b-109">They demonstrate C# best practices.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="be05b-110">命名约定</span><span class="sxs-lookup"><span data-stu-id="be05b-110">Naming Conventions</span></span>  
  
-   <span data-ttu-id="be05b-111">在不包括 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)的短示例中，使用命名空间限定。</span><span class="sxs-lookup"><span data-stu-id="be05b-111">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="be05b-112">如果你知道命名空间默认导入项目中，则不必完全限定来自该命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="be05b-112">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="be05b-113">如果对于单行来说过长，则可以在点 (.) 后中断限定名称，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-113">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     <span data-ttu-id="be05b-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-114">[!code-cs[csProgGuideCodingConventions#1](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_1.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-115">你不必更改通过使用 Visual Studio 设计器工具创建的对象的名称以使它们适合其他准则。</span><span class="sxs-lookup"><span data-stu-id="be05b-115">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="be05b-116">布局约定</span><span class="sxs-lookup"><span data-stu-id="be05b-116">Layout Conventions</span></span>  
 <span data-ttu-id="be05b-117">好的布局利用格式设置来强调代码的结构并使代码更便于阅读。</span><span class="sxs-lookup"><span data-stu-id="be05b-117">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="be05b-118">Microsoft 示例和样本符合以下约定：</span><span class="sxs-lookup"><span data-stu-id="be05b-118">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="be05b-119">使用默认的代码编辑器设置（智能缩进、4 字符缩进、制表符保存为空格）。</span><span class="sxs-lookup"><span data-stu-id="be05b-119">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="be05b-120">有关详细信息，请参阅[选项、文本编辑器、C#、格式设置](/visualstudio/ide/reference/options-text-editor-csharp-formatting)。</span><span class="sxs-lookup"><span data-stu-id="be05b-120">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="be05b-121">每行只写一条语句。</span><span class="sxs-lookup"><span data-stu-id="be05b-121">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="be05b-122">每行只写一个声明。</span><span class="sxs-lookup"><span data-stu-id="be05b-122">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="be05b-123">如果连续行未自动缩进，请将它们缩进一个制表符位（四个空格）。</span><span class="sxs-lookup"><span data-stu-id="be05b-123">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="be05b-124">在方法定义与属性定义之间添加至少一个空白行。</span><span class="sxs-lookup"><span data-stu-id="be05b-124">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="be05b-125">使用括号突出表达式中的子句，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-125">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     <span data-ttu-id="be05b-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-126">[!code-cs[csProgGuideCodingConventions#2](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_2.cs)]</span></span>  
  
## <a name="commenting-conventions"></a><span data-ttu-id="be05b-127">注释约定</span><span class="sxs-lookup"><span data-stu-id="be05b-127">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="be05b-128">将注释放在单独的行上，而非代码行的末尾。</span><span class="sxs-lookup"><span data-stu-id="be05b-128">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="be05b-129">以大写字母开始注释文本。</span><span class="sxs-lookup"><span data-stu-id="be05b-129">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="be05b-130">以句点结束注释文本。</span><span class="sxs-lookup"><span data-stu-id="be05b-130">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="be05b-131">在注释分隔符 (//) 与注释文本之间插入一个空格，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-131">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     <span data-ttu-id="be05b-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-132">[!code-cs[csProgGuideCodingConventions#3](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_3.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-133">不要在注释周围创建格式化的星号块。</span><span class="sxs-lookup"><span data-stu-id="be05b-133">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="be05b-134">语言准则</span><span class="sxs-lookup"><span data-stu-id="be05b-134">Language Guidelines</span></span>  
 <span data-ttu-id="be05b-135">以下各节介绍 C# 遵循以准备代码示例和样本的做法。</span><span class="sxs-lookup"><span data-stu-id="be05b-135">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="be05b-136">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="be05b-136">String Data Type</span></span>  
  
-   <span data-ttu-id="be05b-137">使用 `+` 运算符来连接短字符串，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-137">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     <span data-ttu-id="be05b-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-138">[!code-cs[csProgGuideCodingConventions#6](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_4.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-139">若要在循环中追加字符串，尤其是在使用大量文本时，请使用 <xref:System.Text.StringBuilder> 对象。</span><span class="sxs-lookup"><span data-stu-id="be05b-139">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     <span data-ttu-id="be05b-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-140">[!code-cs[csProgGuideCodingConventions#7](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_5.cs)]</span></span>  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="be05b-141">隐式类型的局部变量</span><span class="sxs-lookup"><span data-stu-id="be05b-141">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="be05b-142">当变量类型明显来自赋值的右侧时，或者当精度类型不重要时，请对本地变量进行[隐式类型化](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="be05b-142">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     <span data-ttu-id="be05b-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-143">[!code-cs[csProgGuideCodingConventions#8](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_6.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-144">当类型并非明显来自赋值的右侧时，请勿使用 [var](../../../csharp/language-reference/keywords/var.md)。</span><span class="sxs-lookup"><span data-stu-id="be05b-144">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     <span data-ttu-id="be05b-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-145">[!code-cs[csProgGuideCodingConventions#9](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_7.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-146">请勿依靠变量名称来指定变量的类型。</span><span class="sxs-lookup"><span data-stu-id="be05b-146">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="be05b-147">它可能不正确。</span><span class="sxs-lookup"><span data-stu-id="be05b-147">It might not be correct.</span></span>  
  
     <span data-ttu-id="be05b-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-148">[!code-cs[csProgGuideCodingConventions#10](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_8.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-149">避免使用 `var` 来代替 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)。</span><span class="sxs-lookup"><span data-stu-id="be05b-149">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="be05b-150">使用隐式类型化来确定 [for](../../../csharp/language-reference/keywords/for.md) 和 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 循环中循环变量的类型。</span><span class="sxs-lookup"><span data-stu-id="be05b-150">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="be05b-151">下面的示例在 `for` 语句中使用隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="be05b-151">The following example uses implicit typing in a `for` statement.</span></span>  
  
     <span data-ttu-id="be05b-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-152">[!code-cs[csProgGuideCodingConventions#11](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_9.cs)]</span></span>  
  
     <span data-ttu-id="be05b-153">下面的示例在 `foreach` 语句中使用隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="be05b-153">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     <span data-ttu-id="be05b-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-154">[!code-cs[csProgGuideCodingConventions#12](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_10.cs)]</span></span>  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="be05b-155">无符号数据类型</span><span class="sxs-lookup"><span data-stu-id="be05b-155">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="be05b-156">通常，使用 `int` 而非无符号类型。</span><span class="sxs-lookup"><span data-stu-id="be05b-156">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="be05b-157">`int` 的使用在整个 C# 中都很常见，并且当你使用 `int` 时，更易于与其他库交互。</span><span class="sxs-lookup"><span data-stu-id="be05b-157">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="be05b-158">数组</span><span class="sxs-lookup"><span data-stu-id="be05b-158">Arrays</span></span>  
  
-   <span data-ttu-id="be05b-159">当在声明行上初始化数组时，请使用简洁的语法。</span><span class="sxs-lookup"><span data-stu-id="be05b-159">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     <span data-ttu-id="be05b-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-160">[!code-cs[csProgGuideCodingConventions#13](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_11.cs)]</span></span>  
  
### <a name="delegates"></a><span data-ttu-id="be05b-161">委托</span><span class="sxs-lookup"><span data-stu-id="be05b-161">Delegates</span></span>  
  
-   <span data-ttu-id="be05b-162">使用简洁的语法来创建委托类型的实例。</span><span class="sxs-lookup"><span data-stu-id="be05b-162">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     <span data-ttu-id="be05b-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-163">[!code-cs[csProgGuideCodingConventions#14](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_12.cs)]</span></span>  
  
     <span data-ttu-id="be05b-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-164">[!code-cs[csProgGuideCodingConventions#15](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_13.cs)]</span></span>  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="be05b-165">异常处理中的 try-catch 和 using 语句</span><span class="sxs-lookup"><span data-stu-id="be05b-165">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="be05b-166">对大多数异常处理使用 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="be05b-166">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     <span data-ttu-id="be05b-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-167">[!code-cs[csProgGuideCodingConventions#16](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_14.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-168">通过使用 C# [using 语句](../../../csharp/language-reference/keywords/using-statement.md)简化你的代码。</span><span class="sxs-lookup"><span data-stu-id="be05b-168">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="be05b-169">如果具有 [try-finally](../../../csharp/language-reference/keywords/try-finally.md) 语句（该语句中 `finally` 块的唯一代码是对 <xref:System.IDisposable.Dispose%2A> 方法的调用），请使用 `using` 语句代替。</span><span class="sxs-lookup"><span data-stu-id="be05b-169">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     <span data-ttu-id="be05b-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-170">[!code-cs[csProgGuideCodingConventions#17](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_15.cs)]</span></span>  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="be05b-171">&& 和 || 运算符</span><span class="sxs-lookup"><span data-stu-id="be05b-171">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="be05b-172">若要通过跳过不必要的比较来避免异常并提高性能，请在执行比较时使用 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)（而不是 [&](../../../csharp/language-reference/operators/and-operator.md)），使用 [||](../../../csharp/language-reference/operators/conditional-or-operator.md) （而不是 [|](../../../csharp/language-reference/operators/or-operator.md)），如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-172">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     <span data-ttu-id="be05b-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-173">[!code-cs[csProgGuideCodingConventions#18](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_16.cs)]</span></span>  
  
### <a name="new-operator"></a><span data-ttu-id="be05b-174">New 运算符</span><span class="sxs-lookup"><span data-stu-id="be05b-174">New Operator</span></span>  
  
-   <span data-ttu-id="be05b-175">隐式类型化时，请使用对象实例化的简洁形式，如下面的声明所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-175">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     <span data-ttu-id="be05b-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-176">[!code-cs[csProgGuideCodingConventions#19](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_17.cs)]</span></span>  
  
     <span data-ttu-id="be05b-177">上一行等同于下面的声明。</span><span class="sxs-lookup"><span data-stu-id="be05b-177">The previous line is equivalent to the following declaration.</span></span>  
  
     <span data-ttu-id="be05b-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-178">[!code-cs[csProgGuideCodingConventions#20](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_18.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-179">使用对象初始值设定项来简化对象创建。</span><span class="sxs-lookup"><span data-stu-id="be05b-179">Use object initializers to simplify object creation.</span></span>  
  
     <span data-ttu-id="be05b-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-180">[!code-cs[csProgGuideCodingConventions#21](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_19.cs)]</span></span>  
  
### <a name="event-handling"></a><span data-ttu-id="be05b-181">事件处理</span><span class="sxs-lookup"><span data-stu-id="be05b-181">Event Handling</span></span>  
  
-   <span data-ttu-id="be05b-182">如果你正定义一个稍后不需要删除的事件处理程序，请使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="be05b-182">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     <span data-ttu-id="be05b-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-183">[!code-cs[csProgGuideCodingConventions#22](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_20.cs)]</span></span>  
  
     <span data-ttu-id="be05b-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-184">[!code-cs[csProgGuideCodingConventions#23](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_21.cs)]</span></span>  
  
### <a name="static-members"></a><span data-ttu-id="be05b-185">静态成员</span><span class="sxs-lookup"><span data-stu-id="be05b-185">Static Members</span></span>  
  
-   <span data-ttu-id="be05b-186">通过使用类名称调用[静态](../../../csharp/language-reference/keywords/static.md)成员：ClassName.StaticMember。</span><span class="sxs-lookup"><span data-stu-id="be05b-186">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="be05b-187">这种做法通过明确静态访问使代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="be05b-187">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="be05b-188">请勿使用派生类的名称限定基类中定义的静态成员。</span><span class="sxs-lookup"><span data-stu-id="be05b-188">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="be05b-189">编译该代码时，代码可读性具有误导性，如果向派生类添加具有相同名称的静态成员，代码可能会被破坏。</span><span class="sxs-lookup"><span data-stu-id="be05b-189">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="be05b-190">LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="be05b-190">LINQ Queries</span></span>  
  
-   <span data-ttu-id="be05b-191">对查询变量使用有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="be05b-191">Use meaningful names for query variables.</span></span> <span data-ttu-id="be05b-192">下面的示例为位于西雅图的客户使用 `seattleCustomers`。</span><span class="sxs-lookup"><span data-stu-id="be05b-192">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     <span data-ttu-id="be05b-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-193">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-194">使用别名确保匿名类型的属性名称都使用 Pascal 大小写格式正确大写。</span><span class="sxs-lookup"><span data-stu-id="be05b-194">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     <span data-ttu-id="be05b-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-195">[!code-cs[csProgGuideCodingConventions#26](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_23.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-196">如果结果中的属性名称模棱两可，请对属性重命名。</span><span class="sxs-lookup"><span data-stu-id="be05b-196">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="be05b-197">例如，如果你的查询返回客户名称和分销商 ID，而不是在结果中将它们保留为 `Name` 和 `ID`，请对它们进行重命名以明确 `Name` 是客户的名称，`ID` 是分销商的 ID。</span><span class="sxs-lookup"><span data-stu-id="be05b-197">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     <span data-ttu-id="be05b-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-198">[!code-cs[csProgGuideCodingConventions#27](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_24.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-199">在查询变量和范围变量的声明中使用隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="be05b-199">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     <span data-ttu-id="be05b-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-200">[!code-cs[csProgGuideCodingConventions#25](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_22.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-201">对齐 [from](../../../csharp/language-reference/keywords/from-clause.md) 子句下的查询子句，如上面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="be05b-201">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="be05b-202">在其他查询子句之前使用 [where](../../../csharp/language-reference/keywords/where-clause.md) 子句，以确保后面的查询子句作用于经过减少和筛选的数据集。</span><span class="sxs-lookup"><span data-stu-id="be05b-202">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     <span data-ttu-id="be05b-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-203">[!code-cs[csProgGuideCodingConventions#29](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_25.cs)]</span></span>  
  
-   <span data-ttu-id="be05b-204">使用多行 `from` 子句代替 [join](../../../csharp/language-reference/keywords/join-clause.md) 子句以访问内部集合。</span><span class="sxs-lookup"><span data-stu-id="be05b-204">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="be05b-205">例如，`Student` 对象的集合可能包含测验分数的集合。</span><span class="sxs-lookup"><span data-stu-id="be05b-205">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="be05b-206">当执行以下查询时，它返回高于 90 的分数，并返回得到该分数的学生的姓氏。</span><span class="sxs-lookup"><span data-stu-id="be05b-206">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     <span data-ttu-id="be05b-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span><span class="sxs-lookup"><span data-stu-id="be05b-207">[!code-cs[csProgGuideCodingConventions#30](../../../csharp/programming-guide/inside-a-program/codesnippet/CSharp/coding-conventions_26.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="be05b-208">安全性</span><span class="sxs-lookup"><span data-stu-id="be05b-208">Security</span></span>  
 <span data-ttu-id="be05b-209">请遵循[安全编码准则](../../../standard/security/secure-coding-guidelines.md)中的准则。</span><span class="sxs-lookup"><span data-stu-id="be05b-209">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be05b-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be05b-210">See Also</span></span>  
 <span data-ttu-id="be05b-211">[Visual Basic 编码约定](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span><span class="sxs-lookup"><span data-stu-id="be05b-211">[Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md) </span></span>  
 [<span data-ttu-id="be05b-212">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="be05b-212">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)

