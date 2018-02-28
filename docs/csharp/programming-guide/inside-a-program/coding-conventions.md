---
title: "C# 编码约定（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- coding conventions, C#
- Visual C#, coding conventions
- C# language, coding conventions
ms.assetid: f4f60de9-d49b-4fb6-bab1-20e19ea24710
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4a8806ddb0a9cc62fe68dc9d558917ee2d532e7f
ms.sourcegitcommit: 75a180acb5d8a2dbd4a52915ce8e980749fb1d05
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2018
---
# <a name="c-coding-conventions-c-programming-guide"></a><span data-ttu-id="6d2b5-102">C# 编码约定（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="6d2b5-102">C# Coding Conventions (C# Programming Guide)</span></span>
 <span data-ttu-id="6d2b5-103">编码约定可实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="6d2b5-103">Coding conventions serve the following purposes:</span></span>  
  
-   <span data-ttu-id="6d2b5-104">它们为代码创建一致的外观，以确保读取器专注于内容而非布局。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-104">They create a consistent look to the code, so that readers can focus on content, not layout.</span></span>  
  
-   <span data-ttu-id="6d2b5-105">它们使得读取器可以通过基于之前的经验进行的假设更快地理解代码。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-105">They enable readers to understand the code more quickly by making assumptions based on previous experience.</span></span>  
  
-   <span data-ttu-id="6d2b5-106">它们便于复制、更改和维护代码。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-106">They facilitate copying, changing, and maintaining the code.</span></span>  
  
-   <span data-ttu-id="6d2b5-107">它们展示 C# 最佳做法。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-107">They demonstrate C# best practices.</span></span>  

 <span data-ttu-id="6d2b5-108">Microsoft 根据本主题中的准则来开发样本和文档。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-108">The guidelines in this topic are used by Microsoft to develop samples and documentation.</span></span>  
  
## <a name="naming-conventions"></a><span data-ttu-id="6d2b5-109">命名约定</span><span class="sxs-lookup"><span data-stu-id="6d2b5-109">Naming Conventions</span></span>  
  
-   <span data-ttu-id="6d2b5-110">在不包括 [using 指令](../../../csharp/language-reference/keywords/using-directive.md)的短示例中，使用命名空间限定。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-110">In short examples that do not include [using directives](../../../csharp/language-reference/keywords/using-directive.md), use namespace qualifications.</span></span> <span data-ttu-id="6d2b5-111">如果你知道命名空间默认导入项目中，则不必完全限定来自该命名空间的名称。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-111">If you know that a namespace is imported by default in a project, you do not have to fully qualify the names from that namespace.</span></span> <span data-ttu-id="6d2b5-112">如果对于单行来说过长，则可以在点 (.) 后中断限定名称，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-112">Qualified names can be broken after a dot (.) if they are too long for a single line, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#1](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#1)]  
  
-   <span data-ttu-id="6d2b5-113">你不必更改通过使用 Visual Studio 设计器工具创建的对象的名称以使它们适合其他准则。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-113">You do not have to change the names of objects that were created by using the Visual Studio designer tools to make them fit other guidelines.</span></span>  
  
## <a name="layout-conventions"></a><span data-ttu-id="6d2b5-114">布局约定</span><span class="sxs-lookup"><span data-stu-id="6d2b5-114">Layout Conventions</span></span>  
 <span data-ttu-id="6d2b5-115">好的布局利用格式设置来强调代码的结构并使代码更便于阅读。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-115">Good layout uses formatting to emphasize the structure of your code and to make the code easier to read.</span></span> <span data-ttu-id="6d2b5-116">Microsoft 示例和样本符合以下约定：</span><span class="sxs-lookup"><span data-stu-id="6d2b5-116">Microsoft examples and samples conform to the following conventions:</span></span>  
  
-   <span data-ttu-id="6d2b5-117">使用默认的代码编辑器设置（智能缩进、4 字符缩进、制表符保存为空格）。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-117">Use the default Code Editor settings (smart indenting, four-character indents, tabs saved as spaces).</span></span> <span data-ttu-id="6d2b5-118">有关详细信息，请参阅[选项、文本编辑器、C#、格式设置](/visualstudio/ide/reference/options-text-editor-csharp-formatting)。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-118">For more information, see [Options, Text Editor, C#, Formatting](/visualstudio/ide/reference/options-text-editor-csharp-formatting).</span></span>  
  
-   <span data-ttu-id="6d2b5-119">每行只写一条语句。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-119">Write only one statement per line.</span></span>  
  
-   <span data-ttu-id="6d2b5-120">每行只写一个声明。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-120">Write only one declaration per line.</span></span>  
  
-   <span data-ttu-id="6d2b5-121">如果连续行未自动缩进，请将它们缩进一个制表符位（四个空格）。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-121">If continuation lines are not indented automatically, indent them one tab stop (four spaces).</span></span>  
  
-   <span data-ttu-id="6d2b5-122">在方法定义与属性定义之间添加至少一个空白行。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-122">Add at least one blank line between method definitions and property definitions.</span></span>  
  
-   <span data-ttu-id="6d2b5-123">使用括号突出表达式中的子句，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-123">Use parentheses to make clauses in an expression apparent, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#2](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#2)]  
  
## <a name="commenting-conventions"></a><span data-ttu-id="6d2b5-124">注释约定</span><span class="sxs-lookup"><span data-stu-id="6d2b5-124">Commenting Conventions</span></span>  
  
-   <span data-ttu-id="6d2b5-125">将注释放在单独的行上，而非代码行的末尾。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-125">Place the comment on a separate line, not at the end of a line of code.</span></span>  
  
-   <span data-ttu-id="6d2b5-126">以大写字母开始注释文本。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-126">Begin comment text with an uppercase letter.</span></span>  
  
-   <span data-ttu-id="6d2b5-127">以句点结束注释文本。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-127">End comment text with a period.</span></span>  
  
-   <span data-ttu-id="6d2b5-128">在注释分隔符 (//) 与注释文本之间插入一个空格，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-128">Insert one space between the comment delimiter (//) and the comment text, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#3](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#3)]  
  
-   <span data-ttu-id="6d2b5-129">不要在注释周围创建格式化的星号块。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-129">Do not create formatted blocks of asterisks around comments.</span></span>  
  
## <a name="language-guidelines"></a><span data-ttu-id="6d2b5-130">语言准则</span><span class="sxs-lookup"><span data-stu-id="6d2b5-130">Language Guidelines</span></span>  
 <span data-ttu-id="6d2b5-131">以下各节介绍 C# 遵循以准备代码示例和样本的做法。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-131">The following sections describe practices that the C# team follows to prepare code examples and samples.</span></span>  
  
### <a name="string-data-type"></a><span data-ttu-id="6d2b5-132">String 数据类型</span><span class="sxs-lookup"><span data-stu-id="6d2b5-132">String Data Type</span></span>  
  
-   <span data-ttu-id="6d2b5-133">使用 `+` 运算符来连接短字符串，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-133">Use the `+` operator to concatenate short strings, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#6](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#6)]  
  
-   <span data-ttu-id="6d2b5-134">若要在循环中追加字符串，尤其是在使用大量文本时，请使用 <xref:System.Text.StringBuilder> 对象。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-134">To append strings in loops, especially when you are working with large amounts of text, use a <xref:System.Text.StringBuilder> object.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#7](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#7)]  
  
### <a name="implicitly-typed-local-variables"></a><span data-ttu-id="6d2b5-135">隐式类型的局部变量</span><span class="sxs-lookup"><span data-stu-id="6d2b5-135">Implicitly Typed Local Variables</span></span>  
  
-   <span data-ttu-id="6d2b5-136">当变量类型明显来自赋值的右侧时，或者当精度类型不重要时，请对本地变量进行[隐式类型化](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-136">Use [implicit typing](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) for local variables when the type of the variable is obvious from the right side of the assignment, or when the precise type is not important.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#8](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#8)]  
  
-   <span data-ttu-id="6d2b5-137">当类型并非明显来自赋值的右侧时，请勿使用 [var](../../../csharp/language-reference/keywords/var.md)。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-137">Do not use [var](../../../csharp/language-reference/keywords/var.md) when the type is not apparent from the right side of the assignment.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#9](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#9)]  
  
-   <span data-ttu-id="6d2b5-138">请勿依靠变量名称来指定变量的类型。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-138">Do not rely on the variable name to specify the type of the variable.</span></span> <span data-ttu-id="6d2b5-139">它可能不正确。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-139">It might not be correct.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#10](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#10)]  
  
-   <span data-ttu-id="6d2b5-140">避免使用 `var` 来代替 [dynamic](../../../csharp/language-reference/keywords/dynamic.md)。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-140">Avoid the use of `var` in place of [dynamic](../../../csharp/language-reference/keywords/dynamic.md).</span></span>  
  
-   <span data-ttu-id="6d2b5-141">使用隐式类型化来确定 [for](../../../csharp/language-reference/keywords/for.md) 和 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 循环中循环变量的类型。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-141">Use implicit typing to determine the type of the loop variable in [for](../../../csharp/language-reference/keywords/for.md) and [foreach](../../../csharp/language-reference/keywords/foreach-in.md) loops.</span></span>  
  
     <span data-ttu-id="6d2b5-142">下面的示例在 `for` 语句中使用隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-142">The following example uses implicit typing in a `for` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#11](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#11)]  
  
     <span data-ttu-id="6d2b5-143">下面的示例在 `foreach` 语句中使用隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-143">The following example uses implicit typing in a `foreach` statement.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#12](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#12)]  
  
### <a name="unsigned-data-type"></a><span data-ttu-id="6d2b5-144">无符号数据类型</span><span class="sxs-lookup"><span data-stu-id="6d2b5-144">Unsigned Data Type</span></span>  
  
-   <span data-ttu-id="6d2b5-145">通常，使用 `int` 而非无符号类型。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-145">In general, use `int` rather than unsigned types.</span></span> <span data-ttu-id="6d2b5-146">`int` 的使用在整个 C# 中都很常见，并且当你使用 `int` 时，更易于与其他库交互。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-146">The use of `int` is common throughout C#, and it is easier to interact with other libraries when you use `int`.</span></span>  
  
### <a name="arrays"></a><span data-ttu-id="6d2b5-147">数组</span><span class="sxs-lookup"><span data-stu-id="6d2b5-147">Arrays</span></span>  
  
-   <span data-ttu-id="6d2b5-148">当在声明行上初始化数组时，请使用简洁的语法。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-148">Use the concise syntax when you initialize arrays on the declaration line.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#13](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#13)]  
  
### <a name="delegates"></a><span data-ttu-id="6d2b5-149">委托</span><span class="sxs-lookup"><span data-stu-id="6d2b5-149">Delegates</span></span>  
  
-   <span data-ttu-id="6d2b5-150">使用简洁的语法来创建委托类型的实例。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-150">Use the concise syntax to create instances of a delegate type.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#14](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#14)]  
  
     [!code-csharp[csProgGuideCodingConventions#15](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#15)]  
  
### <a name="try-catch-and-using-statements-in-exception-handling"></a><span data-ttu-id="6d2b5-151">异常处理中的 try-catch 和 using 语句</span><span class="sxs-lookup"><span data-stu-id="6d2b5-151">try-catch and using Statements in Exception Handling</span></span>  
  
-   <span data-ttu-id="6d2b5-152">对大多数异常处理使用 [try-catch](../../../csharp/language-reference/keywords/try-catch.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-152">Use a [try-catch](../../../csharp/language-reference/keywords/try-catch.md) statement for most exception handling.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#16](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#16)]  
  
-   <span data-ttu-id="6d2b5-153">通过使用 C# [using 语句](../../../csharp/language-reference/keywords/using-statement.md)简化你的代码。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-153">Simplify your code by using the C# [using statement](../../../csharp/language-reference/keywords/using-statement.md).</span></span> <span data-ttu-id="6d2b5-154">如果具有 [try-finally](../../../csharp/language-reference/keywords/try-finally.md) 语句（该语句中 `finally` 块的唯一代码是对 <xref:System.IDisposable.Dispose%2A> 方法的调用），请使用 `using` 语句代替。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-154">If you have a [try-finally](../../../csharp/language-reference/keywords/try-finally.md) statement in which the only code in the `finally` block is a call to the <xref:System.IDisposable.Dispose%2A> method, use a `using` statement instead.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#17](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#17)]  
  
### <a name="-and-124124-operators"></a><span data-ttu-id="6d2b5-155">&& 和 || 运算符</span><span class="sxs-lookup"><span data-stu-id="6d2b5-155">&& and &#124;&#124; Operators</span></span>  
  
-   <span data-ttu-id="6d2b5-156">若要通过跳过不必要的比较来避免异常并提高性能，请在执行比较时使用 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)（而不是 [&](../../../csharp/language-reference/operators/and-operator.md)），使用 [||](../../../csharp/language-reference/operators/conditional-or-operator.md) （而不是 [|](../../../csharp/language-reference/operators/or-operator.md)），如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-156">To avoid exceptions and increase performance by skipping unnecessary comparisons, use [&&](../../../csharp/language-reference/operators/conditional-and-operator.md) instead of [&](../../../csharp/language-reference/operators/and-operator.md) and [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md) instead of [&#124;](../../../csharp/language-reference/operators/or-operator.md) when you perform comparisons, as shown in the following example.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#18](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#18)]  
  
### <a name="new-operator"></a><span data-ttu-id="6d2b5-157">New 运算符</span><span class="sxs-lookup"><span data-stu-id="6d2b5-157">New Operator</span></span>  
  
-   <span data-ttu-id="6d2b5-158">隐式类型化时，请使用对象实例化的简洁形式，如下面的声明所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-158">Use the concise form of object instantiation, with implicit typing, as shown in the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#19](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#19)]  
  
     <span data-ttu-id="6d2b5-159">上一行等同于下面的声明。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-159">The previous line is equivalent to the following declaration.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#20](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#20)]  
  
-   <span data-ttu-id="6d2b5-160">使用对象初始值设定项来简化对象创建。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-160">Use object initializers to simplify object creation.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#21](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#21)]  
  
### <a name="event-handling"></a><span data-ttu-id="6d2b5-161">事件处理</span><span class="sxs-lookup"><span data-stu-id="6d2b5-161">Event Handling</span></span>  
  
-   <span data-ttu-id="6d2b5-162">如果你正定义一个稍后不需要删除的事件处理程序，请使用 lambda 表达式。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-162">If you are defining an event handler that you do not need to remove later, use a lambda expression.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#22](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#22)]  
  
     [!code-csharp[csProgGuideCodingConventions#23](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#23)]  
  
### <a name="static-members"></a><span data-ttu-id="6d2b5-163">静态成员</span><span class="sxs-lookup"><span data-stu-id="6d2b5-163">Static Members</span></span>  
  
-   <span data-ttu-id="6d2b5-164">通过使用类名称调用[静态](../../../csharp/language-reference/keywords/static.md)成员：ClassName.StaticMember。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-164">Call [static](../../../csharp/language-reference/keywords/static.md) members by using the class name: *ClassName.StaticMember*.</span></span> <span data-ttu-id="6d2b5-165">这种做法通过明确静态访问使代码更易于阅读。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-165">This practice makes code more readable by making static access clear.</span></span>  <span data-ttu-id="6d2b5-166">请勿使用派生类的名称限定基类中定义的静态成员。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-166">Do not qualify a static member defined in a base class with the name of a derived class.</span></span>  <span data-ttu-id="6d2b5-167">编译该代码时，代码可读性具有误导性，如果向派生类添加具有相同名称的静态成员，代码可能会被破坏。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-167">While that code compiles, the code readability is misleading, and the code may break in the future if you add a static member with the same name to the derived class.</span></span>  
  
### <a name="linq-queries"></a><span data-ttu-id="6d2b5-168">LINQ 查询</span><span class="sxs-lookup"><span data-stu-id="6d2b5-168">LINQ Queries</span></span>  
  
-   <span data-ttu-id="6d2b5-169">对查询变量使用有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-169">Use meaningful names for query variables.</span></span> <span data-ttu-id="6d2b5-170">下面的示例为位于西雅图的客户使用 `seattleCustomers`。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-170">The following example uses `seattleCustomers` for customers who are located in Seattle.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="6d2b5-171">使用别名确保匿名类型的属性名称都使用 Pascal 大小写格式正确大写。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-171">Use aliases to make sure that property names of anonymous types are correctly capitalized, using Pascal casing.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#26](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#26)]  
  
-   <span data-ttu-id="6d2b5-172">如果结果中的属性名称模棱两可，请对属性重命名。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-172">Rename properties when the property names in the result would be ambiguous.</span></span> <span data-ttu-id="6d2b5-173">例如，如果你的查询返回客户名称和分销商 ID，而不是在结果中将它们保留为 `Name` 和 `ID`，请对它们进行重命名以明确 `Name` 是客户的名称，`ID` 是分销商的 ID。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-173">For example, if your query returns a customer name and a distributor ID, instead of leaving them as `Name` and `ID` in the result, rename them to clarify that `Name` is the name of a customer, and `ID` is the ID of a distributor.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#27](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#27)]  
  
-   <span data-ttu-id="6d2b5-174">在查询变量和范围变量的声明中使用隐式类型化。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-174">Use implicit typing in the declaration of query variables and range variables.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#25](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#25)]  
  
-   <span data-ttu-id="6d2b5-175">对齐 [from](../../../csharp/language-reference/keywords/from-clause.md) 子句下的查询子句，如上面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-175">Align query clauses under the [from](../../../csharp/language-reference/keywords/from-clause.md) clause, as shown in the previous examples.</span></span>  
  
-   <span data-ttu-id="6d2b5-176">在其他查询子句之前使用 [where](../../../csharp/language-reference/keywords/where-clause.md) 子句，以确保后面的查询子句作用于经过减少和筛选的数据集。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-176">Use [where](../../../csharp/language-reference/keywords/where-clause.md) clauses before other query clauses to ensure that later query clauses operate on the reduced, filtered set of data.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#29](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#29)]  
  
-   <span data-ttu-id="6d2b5-177">使用多行 `from` 子句代替 [join](../../../csharp/language-reference/keywords/join-clause.md) 子句以访问内部集合。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-177">Use multiple `from` clauses instead of a [join](../../../csharp/language-reference/keywords/join-clause.md) clause to access inner collections.</span></span> <span data-ttu-id="6d2b5-178">例如，`Student` 对象的集合可能包含测验分数的集合。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-178">For example, a collection of `Student` objects might each contain a collection of test scores.</span></span> <span data-ttu-id="6d2b5-179">当执行以下查询时，它返回高于 90 的分数，并返回得到该分数的学生的姓氏。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-179">When the following query is executed, it returns each score that is over 90, along with the last name of the student who received the score.</span></span>  
  
     [!code-csharp[csProgGuideCodingConventions#30](../../../../samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidecodingconventions/cs/program.cs#30)]  
  
## <a name="security"></a><span data-ttu-id="6d2b5-180">安全性</span><span class="sxs-lookup"><span data-stu-id="6d2b5-180">Security</span></span>  
 <span data-ttu-id="6d2b5-181">请遵循[安全编码准则](../../../standard/security/secure-coding-guidelines.md)中的准则。</span><span class="sxs-lookup"><span data-stu-id="6d2b5-181">Follow the guidelines in [Secure Coding Guidelines](../../../standard/security/secure-coding-guidelines.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d2b5-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="6d2b5-182">See Also</span></span>  
 [<span data-ttu-id="6d2b5-183">Visual Basic 编码约定</span><span class="sxs-lookup"><span data-stu-id="6d2b5-183">Visual Basic Coding Conventions</span></span>](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 [<span data-ttu-id="6d2b5-184">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="6d2b5-184">Secure Coding Guidelines</span></span>](../../../standard/security/secure-coding-guidelines.md)
