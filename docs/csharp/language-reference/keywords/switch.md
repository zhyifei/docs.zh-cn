---
title: C# switch 语句
ms.date: 08/14/2018
f1_keywords:
- switch_CSharpKeyword
- switch
- case
- case_CSharpKeyword
helpviewer_keywords:
- switch statement [C#]
- switch keyword [C#]
- case statement [C#]
- default keyword [C#]
ms.assetid: 44bae8b8-8841-4d85-826b-8a94277daecb
ms.openlocfilehash: 73524fd54aeffc86fe0c451ec4418308da764682
ms.sourcegitcommit: 7156c0b9e4ce4ce5ecf48ce3d925403b638b680c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "58463249"
---
# <a name="switch-c-reference"></a><span data-ttu-id="c1c2c-102">switch（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c1c2c-102">switch (C# reference)</span></span>

<span data-ttu-id="c1c2c-103">`switch` 是一个选择语句，它根据与匹配表达式匹配的模式，从候选列表中选择单个开关部分进行执行。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-103">`switch` is a selection statement that chooses a single *switch section* to execute from a list of candidates based on a pattern match with the *match expression*.</span></span>

[!code-csharp[switch#1](~/samples/snippets/csharp/language-reference/keywords/switch/switch1.cs#1)]

<span data-ttu-id="c1c2c-104">如果针对 3 个或更多条件测试单个表达式，`switch` 语句通常用作 [if-else](if-else.md) 构造的替代项。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-104">The `switch` statement is often used as an alternative to an [if-else](if-else.md) construct if a single expression is tested against three or more conditions.</span></span> <span data-ttu-id="c1c2c-105">例如，以下 `switch` 语句确定类型为 `Color` 的变量是否具有三个值之一：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-105">For example, the following `switch` statement determines whether a variable of type `Color` has one of three values:</span></span>

[!code-csharp[switch#3](~/samples/snippets/csharp/language-reference/keywords/switch/switch3.cs#1)]

<span data-ttu-id="c1c2c-106">它等效于使用 `if`- `else` 构造的以下示例。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-106">It is equivalent to the following example that uses an `if`-`else` construct.</span></span>

[!code-csharp[switch#3a](~/samples/snippets/csharp/language-reference/keywords/switch/switch3a.cs#1)]

## <a name="the-match-expression"></a><span data-ttu-id="c1c2c-107">匹配表达式</span><span class="sxs-lookup"><span data-stu-id="c1c2c-107">The match expression</span></span>

<span data-ttu-id="c1c2c-108">匹配表达式提供与 `case` 标签中的模式相匹配的值。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-108">The match expression provides the value to match against the patterns in `case` labels.</span></span> <span data-ttu-id="c1c2c-109">语法为：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-109">Its syntax is:</span></span>

```csharp
   switch (expr)
```

<span data-ttu-id="c1c2c-110">在 C# 6 中，匹配表达式必须是返回以下类型值的表达式：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-110">In C# 6, the match expression must be an expression that returns a value of the following types:</span></span>

- <span data-ttu-id="c1c2c-111">[字符型](char.md)。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-111">a [char](char.md).</span></span>
- <span data-ttu-id="c1c2c-112">[字符串](string.md)。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-112">a [string](string.md).</span></span>
- <span data-ttu-id="c1c2c-113">[bool](bool.md)。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-113">a [bool](bool.md).</span></span>
- <span data-ttu-id="c1c2c-114">整数值，例如 [int](int.md) 或 [long](long.md)。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-114">an integral value, such as an [int](int.md) or a [long](long.md).</span></span>
- <span data-ttu-id="c1c2c-115">[枚举](enum.md)值。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-115">an [enum](enum.md) value.</span></span>

<span data-ttu-id="c1c2c-116">从 C# 7.0 开始，匹配表达式可以是任何非 null 表达式。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-116">Starting with C# 7.0, the match expression can be any non-null expression.</span></span>

## <a name="the-switch-section"></a><span data-ttu-id="c1c2c-117">开关部分</span><span class="sxs-lookup"><span data-stu-id="c1c2c-117">The switch section</span></span>

<span data-ttu-id="c1c2c-118">`switch` 语句包含一个或多个开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-118">A `switch` statement includes one or more switch sections.</span></span> <span data-ttu-id="c1c2c-119">每个 switch 部分包含一个或多个 case 标签（case 或 default 标签），后接一个或多个语句。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-119">Each switch section contains one or more *case labels* (either a case or default label) followed by one or more statements.</span></span> <span data-ttu-id="c1c2c-120">`switch` 语句最多可包含一个置于任何 switch 部分中的 default 标签。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-120">The `switch` statement may include at most one default label placed in any switch section.</span></span> <span data-ttu-id="c1c2c-121">以下示例显示了一个简单的 `switch` 语句，该语句包含三个 switch 部分，每个部分包含两个语句。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-121">The following example shows a simple `switch` statement that has three switch sections, each containing two statements.</span></span> <span data-ttu-id="c1c2c-122">第二个 switch 部分包含 `case 2:` 和 `case 3:` 标签。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-122">The second switch section contains the `case 2:` and `case 3:` labels.</span></span>

<span data-ttu-id="c1c2c-123">`switch` 语句中可以包含任意数量的开关部分，每个开关部分可以具有一个或多个 case 标签，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-123">A `switch` statement can include any number of switch sections, and each section can have one or more case labels, as shown in the following example.</span></span> <span data-ttu-id="c1c2c-124">但是，任何两个 case 标签不可包含相同的表达式。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-124">However, no two case labels may contain the same expression.</span></span>

[!code-csharp[switch#2](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch2.cs#1)]

<span data-ttu-id="c1c2c-125">switch 语句执行中只有一个开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-125">Only one switch section in a switch statement executes.</span></span> <span data-ttu-id="c1c2c-126">C# 不允许从一个开关部分继续执行到下一个开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-126">C# does not allow execution to continue from one switch section to the next.</span></span> <span data-ttu-id="c1c2c-127">因此，下面的代码生成编译器错误 CS0163：“控制不能从一个 case 标签（\<case 标签 >）贯穿到另一个 case 标签。”</span><span class="sxs-lookup"><span data-stu-id="c1c2c-127">Because of this, the following code generates a compiler error, CS0163: "Control cannot fall through from one case label (\<case label>) to another."</span></span>

```csharp
switch (caseSwitch)
{
    // The following switch section causes an error.
    case 1:
        Console.WriteLine("Case 1...");
        // Add a break or other jump statement here.
    case 2:
        Console.WriteLine("... and/or Case 2");
        break;
}
```

<span data-ttu-id="c1c2c-128">通常通过使用 [break](break.md)、[goto](goto.md) 或 [return](return.md) 语句显式退出开关部分来满足此要求。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-128">This requirement is usually met by explicitly exiting the switch section by using a [break](break.md), [goto](goto.md), or [return](return.md) statement.</span></span> <span data-ttu-id="c1c2c-129">但是，以下代码也有效，因为它确保程序控件不能贯穿 `default` 开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-129">However, the following code is also valid, because it ensures that program control cannot fall through to the `default` switch section.</span></span>

[!code-csharp[switch#4](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch4.cs#1)]

<span data-ttu-id="c1c2c-130">在 case 标签与匹配表达式匹配的开关部分中执行语句列表时，先执行第一个语句，再执行整个语句列表，通常执行到跳转语句（如 `break`、`goto case`、`goto label`、`return` 或 `throw`）为止。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-130">Execution of the statement list in the switch section with a case label that matches the match expression begins with the first statement and proceeds through the statement list, typically until a jump statement, such as a `break`, `goto case`, `goto label`, `return`, or `throw`, is reached.</span></span> <span data-ttu-id="c1c2c-131">此时，控件在 `switch` 语句之外进行传输或传输到另一个 case 标签。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-131">At that point, control is transferred outside the `switch` statement or to another case label.</span></span> <span data-ttu-id="c1c2c-132">如果使用 `goto` 语句，必须将控制权移交给常数标签。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-132">A `goto` statement, if it is used, must transfer control to a constant label.</span></span> <span data-ttu-id="c1c2c-133">此限制是必要的，因为尝试将控制权移交给非常数标签可能会产生不良的副作用，如将控制权移交给代码中的意外位置，或创建无限循环。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-133">This restriction is necessary, since attempting to transfer control to a non-constant label can have undesirable side-effects, such transferring control to an unintended location in code or creating an endless loop.</span></span>

## <a name="case-labels"></a><span data-ttu-id="c1c2c-134">Case 标签</span><span class="sxs-lookup"><span data-stu-id="c1c2c-134">Case labels</span></span>

<span data-ttu-id="c1c2c-135">每个 case 标签指定一个模式与匹配表达式（前面示例中的 `caseSwitch` 变量）进行比较。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-135">Each case label specifies a pattern to compare to the match expression (the `caseSwitch` variable in the previous examples).</span></span> <span data-ttu-id="c1c2c-136">如果它们匹配，则将控件传输到包含**首次**匹配 case 标签的开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-136">If they match, control is transferred to the switch section that contains the **first** matching case label.</span></span> <span data-ttu-id="c1c2c-137">如果 case 标签模式均不与匹配表达式相匹配，控件将传输到带 `default` case 标签的部分（如有）。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-137">If no case label pattern matches the match expression, control is transferred to the section with the `default` case label, if there is one.</span></span> <span data-ttu-id="c1c2c-138">如果没有 `default` case，将不会执行任何开关部分中的语句，并且会将控件传输到 `switch` 语句之外。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-138">If there is no `default` case, no statements in any switch section are executed, and control is transferred outside the `switch` statement.</span></span>

<span data-ttu-id="c1c2c-139">有关 `switch` 语句和模式匹配的信息，请参阅使用 `switch` 语句的 [模式匹配](#pattern)部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-139">For information on the `switch` statement and pattern matching, see the [Pattern matching with the `switch` statement](#pattern) section.</span></span>

<span data-ttu-id="c1c2c-140">因为 C# 6 仅支持常量模式并且不允许重复常量值，所以 case 标签定义了互斥值，而且仅有一个模式可与匹配表达式相匹配。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-140">Because C# 6 supports only the constant pattern and does not allow the repetition of constant values, case labels define mutually exclusive values, and only one pattern can match the match expression.</span></span> <span data-ttu-id="c1c2c-141">因此，`case` 语句显示的顺序并不重要。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-141">As a result, the order in which `case` statements appear is unimportant.</span></span>

<span data-ttu-id="c1c2c-142">然而，在 C# 7.0 中，因为支持其他模式，所以 case 标签不需要定义互斥值，并且多个模式可以与匹配表达式相匹配。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-142">In C# 7.0, however, because other patterns are supported, case labels need not define mutually exclusive values, and multiple patterns can match the match expression.</span></span> <span data-ttu-id="c1c2c-143">因为仅执行包含匹配模式的首次开关部分中的语句，所以 `case` 语句显示的顺序很重要。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-143">Because only the statements in the first switch section that contains the matching pattern are executed, the order in which `case` statements appear is now important.</span></span> <span data-ttu-id="c1c2c-144">如果 C# 检测到开关部分的 case 语句或语句等效于或是先前语句的子集，它将生成编译错误 CS8120：“开关 case 已由先前 case 处理。”</span><span class="sxs-lookup"><span data-stu-id="c1c2c-144">If C# detects a switch section whose case statement or statements are equivalent to or are subsets of previous statements, it generates a compiler error, CS8120, "The switch case has already been handled by a previous case."</span></span>

<span data-ttu-id="c1c2c-145">以下示例说明了使用各种非互斥模式的 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-145">The following example illustrates a `switch` statement that uses a variety of non-mutually exclusive patterns.</span></span> <span data-ttu-id="c1c2c-146">如果移动 `case 0:` 开关部分，使其不再是 `switch` 语句中的第一部分，C# 会生成编译器错误，因为值为零的整数是所有整数的子集（由 `case int val` 语句定义的模式）。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-146">If you move the `case 0:` switch section so that it is no longer the first section in the `switch` statement, C# generates a compiler error because an integer whose value is zero is a subset of all integers, which is the pattern defined by the `case int val` statement.</span></span>

[!code-csharp[switch#5](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch5.cs#1)]

<span data-ttu-id="c1c2c-147">你可以通过以下两种方法之一更正此问题并消除编译器警告：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-147">You can correct this issue and eliminate the compiler warning in one of two ways:</span></span>

- <span data-ttu-id="c1c2c-148">更改开关部分的顺序。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-148">By changing the order of the switch sections.</span></span>

- <span data-ttu-id="c1c2c-149">在 `case` 标签中使用 [when clause](#when) 子句。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-149">By using a [when clause](#when) in the `case` label.</span></span>

## <a name="the-default-case"></a><span data-ttu-id="c1c2c-150">`default` case</span><span class="sxs-lookup"><span data-stu-id="c1c2c-150">The `default` case</span></span>

<span data-ttu-id="c1c2c-151">如果匹配表达式与任何其他 `case` 标签不匹配，则 `default` case 指定要执行的开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-151">The `default` case specifies the switch section to execute if the match expression does not match any other `case` label.</span></span> <span data-ttu-id="c1c2c-152">如果不存在 `default` case，并且匹配表达式与其他任何 `case` 标签都不匹配，则程序流将贯穿 `switch` 语句。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-152">If a `default` case is not present and the match expression does not match any other `case` label, program flow falls through the `switch` statement.</span></span>

<span data-ttu-id="c1c2c-153">`default` case 可以在 `switch` 语句中以任何顺序显示。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-153">The `default` case can appear in any order in the `switch` statement.</span></span> <span data-ttu-id="c1c2c-154">无论其在源代码中的顺序如何，都将在对所有 `case` 标签进行计算之后，最后对其进行计算。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-154">Regardless of its order in the source code, it is always evaluated last, after all `case` labels have been evaluated.</span></span>

## <a name="a-namepattern--pattern-matching-with-the-switch-statement"></a><span data-ttu-id="c1c2c-155">使用 `switch` 语句的 <a name="pattern" /> 模式匹配</span><span class="sxs-lookup"><span data-stu-id="c1c2c-155"><a name="pattern" /> Pattern matching with the `switch` statement</span></span>

<span data-ttu-id="c1c2c-156">每个 `case` 语句定义一个模式，如果它与匹配表达式相匹配，则会导致执行其包含的开关部分。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-156">Each `case` statement defines a pattern that, if it matches the match expression, causes its  containing switch section to be executed.</span></span> <span data-ttu-id="c1c2c-157">所有版本的 C# 都支持常量模式。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-157">All versions of C# support the constant pattern.</span></span> <span data-ttu-id="c1c2c-158">其余模式从 C# 7.0 开始支持。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-158">The remaining patterns are supported beginning with C# 7.0.</span></span>

### <a name="constant-pattern"></a><span data-ttu-id="c1c2c-159">常量模式</span><span class="sxs-lookup"><span data-stu-id="c1c2c-159">Constant pattern</span></span>

<span data-ttu-id="c1c2c-160">常量模式测试匹配表达式是否等于指定常量。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-160">The constant pattern tests whether the match expression equals a specified constant.</span></span> <span data-ttu-id="c1c2c-161">语法为：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-161">Its syntax is:</span></span>

```csharp
   case constant:
```

<span data-ttu-id="c1c2c-162">其中 *constant* 是要测试的值。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-162">where *constant* is the value to test for.</span></span> <span data-ttu-id="c1c2c-163">*constant* 可以是以下任何常数表达式：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-163">*constant* can be any of the following constant expressions:</span></span>

- <span data-ttu-id="c1c2c-164">[bool](bool.md) 文本，为 `true` 或 `false`。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-164">A [bool](bool.md) literal, either `true` or `false`.</span></span>
- <span data-ttu-id="c1c2c-165">任何整数常量，例如 [int](int.md)、[long](long.md) 或[字节](byte.md)。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-165">Any integral constant, such as an [int](int.md), a [long](long.md), or a [byte](byte.md).</span></span>
- <span data-ttu-id="c1c2c-166">已声明 `const` 变量的名称。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-166">The name of a declared `const` variable.</span></span>
- <span data-ttu-id="c1c2c-167">一个枚举常量。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-167">An enumeration constant.</span></span>
- <span data-ttu-id="c1c2c-168">[字符型](char.md)文本。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-168">A [char](char.md) literal.</span></span>
- <span data-ttu-id="c1c2c-169">[字符串](string.md)文本。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-169">A [string](string.md) literal.</span></span>

<span data-ttu-id="c1c2c-170">常数表达式的计算方式如下：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-170">The constant expression is evaluated as follows:</span></span>

- <span data-ttu-id="c1c2c-171">如果 *expr* 和 *constant* 均为整型类型，则 C# 相等运算符确定表示式是否返回 `true`（即，是否为 `expr == constant`）。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-171">If *expr* and *constant* are integral types, the C# equality operator determines whether the expression returns `true` (that is, whether `expr == constant`).</span></span>

- <span data-ttu-id="c1c2c-172">否则，由对静态 [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) 方法的调用确定表达式的值。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-172">Otherwise, the value of the expression is determined by a call to the static [Object.Equals(expr, constant)](xref:System.Object.Equals(System.Object,System.Object)) method.</span></span>

<span data-ttu-id="c1c2c-173">以下示例使用常量模式来确定特定日期是否为周末、工作周的第一天、工作周的最后一天或工作周的中间日期。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-173">The following example uses the constant pattern to determine whether a particular date is a weekend, the first day of the work week, the last day of the work week, or the middle of the work week.</span></span> <span data-ttu-id="c1c2c-174">它根据 <xref:System.DayOfWeek> 枚举的成员计算当前日期的 <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-174">It evaluates the <xref:System.DateTime.DayOfWeek?displayProperty=nameWithType> property of the current day against the members of the <xref:System.DayOfWeek> enumeration.</span></span>

[!code-csharp[switch#7](../../../../samples/snippets/csharp/language-reference/keywords/switch/const-pattern.cs#1)]

<span data-ttu-id="c1c2c-175">以下示例使用常量模式在模拟自动咖啡机的控制台应用程序中处理用户输入。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-175">The following example uses the constant pattern to handle user input in a console application that simulates an automatic coffee machine.</span></span>

[!code-csharp[switch#6](../../../../samples/snippets/csharp/language-reference/keywords/switch/switch6.cs)]

### <a name="type-pattern"></a><span data-ttu-id="c1c2c-176">类型模式</span><span class="sxs-lookup"><span data-stu-id="c1c2c-176">Type pattern</span></span>

<span data-ttu-id="c1c2c-177">类型模式可启用简洁类型计算和转换。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-177">The type pattern enables concise type evaluation and conversion.</span></span> <span data-ttu-id="c1c2c-178">使用 `switch` 语句执行模式匹配时，会测试表达式是否可转换为指定类型，如果可以，则将其转换为该类型的一个变量。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-178">When used with the `switch` statement to perform pattern matching, it tests whether an expression can be converted to a specified type and, if it can be, casts it to a variable of that type.</span></span> <span data-ttu-id="c1c2c-179">语法为：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-179">Its syntax is:</span></span>

```csharp
   case type varname
```

<span data-ttu-id="c1c2c-180">其中 *type* 是 *expr* 结果要转换到的类型的名称，*varname* 是 *expr* 结果要转换到的对象（如果匹配成功）。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-180">where *type* is the name of the type to which the result of *expr* is to be converted, and *varname* is the object to which the result of *expr* is converted if the match succeeds.</span></span>

<span data-ttu-id="c1c2c-181">如果以下任一条件成立，则 `case` 表达式为 `true`：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-181">The `case` expression is `true` if any of the following is true:</span></span>

- <span data-ttu-id="c1c2c-182">*expr* 是与 *type* 具有相同类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-182">*expr* is an instance of the same type as *type*.</span></span>

- <span data-ttu-id="c1c2c-183">*expr* 是派生自 *type* 的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-183">*expr* is an instance of a type that derives from *type*.</span></span> <span data-ttu-id="c1c2c-184">换言之，*expr* 结果可以向上转换为 *type* 的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-184">In other words, the result of *expr* can be upcast to an instance of *type*.</span></span>

- <span data-ttu-id="c1c2c-185">*expr* 具有属于 *type* 的一个基类的编译时类型，*expr* 还具有属于 *type* 或派生自 *type* 的运行时类型。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-185">*expr* has a compile-time type that is a base class of *type*, and *expr* has a runtime type that is *type* or is derived from *type*.</span></span> <span data-ttu-id="c1c2c-186">变量的编译时类型是其类型声明中定义的变量类型。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-186">The *compile-time type* of a variable is the variable's type as defined in its type declaration.</span></span> <span data-ttu-id="c1c2c-187">变量的运行时类型是分配给该变量的实例类型。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-187">The *runtime type* of a variable is the type of the instance that is assigned to that variable.</span></span>

- <span data-ttu-id="c1c2c-188">*expr* 是实现 *type* 接口的类型的一个实例。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-188">*expr* is an instance of a type that implements the *type* interface.</span></span>

<span data-ttu-id="c1c2c-189">如果 case 表达式为 true，将会明确分配 *varname*，并且仅在开关部分中具有本地作用域。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-189">If the case expression is true, *varname* is definitely assigned and has local scope within the switch section only.</span></span>

<span data-ttu-id="c1c2c-190">请注意，`null` 与任何类型都不匹配。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-190">Note that `null` does not match a type.</span></span> <span data-ttu-id="c1c2c-191">若要匹配 `null`，请使用以下 `case` 标签：</span><span class="sxs-lookup"><span data-stu-id="c1c2c-191">To match a `null`, you use the following `case` label:</span></span>

```csharp
case null:
```

<span data-ttu-id="c1c2c-192">以下示例使用类型模式来提供有关各种集合类型的信息。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-192">The following example uses the type pattern to provide information about various kinds of collection types.</span></span>

[!code-csharp[type-pattern#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern.cs#1)]

<span data-ttu-id="c1c2c-193">如果没有模式匹配，则可能按以下方式编写此代码。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-193">Without pattern matching, this code might be written as follows.</span></span> <span data-ttu-id="c1c2c-194">使用类型模式匹配可消除测试转换结果是否为 `null` 或执行重复转换的必要，从而生成更紧凑易读的代码。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-194">The use of type pattern matching produces more compact, readable code by eliminating the need to test whether the result of a conversion is a `null` or to perform repeated casts.</span></span>

[!code-csharp[type-pattern2#1](~/samples/snippets/csharp/language-reference/keywords/switch/type-pattern2.cs#1)]

## <a name="a-namewhen--the-case-statement-and-the-when-clause"></a><span data-ttu-id="c1c2c-195"><a name="when" /> `case` 语句和 `when` 子句</span><span class="sxs-lookup"><span data-stu-id="c1c2c-195"><a name="when" /> The `case` statement and the `when` clause</span></span>

<span data-ttu-id="c1c2c-196">从 C# 7.0 开始，因为 case 语句不需要互相排斥，因此可以添加 `when` 子句来指定必须满足的附加条件使 case 语句计算为 true。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-196">Starting with C# 7.0, because case statements need not be mutually exclusive, you can add a `when` clause to specify an additional condition that must be satisfied for the case statement to evaluate to true.</span></span> <span data-ttu-id="c1c2c-197">`when` 子句可以是返回布尔值的任何表达式。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-197">The `when` clause can be any expression that returns a Boolean value.</span></span>

<span data-ttu-id="c1c2c-198">下面的示例定义了 `Shape` 基类、从 `Shape` 派生的 `Rectangle` 类以及从 `Rectangle` 派生的 `Square` 类。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-198">The following example defines a base `Shape` class, a `Rectangle` class that derives from `Shape`, and a `Square` class that derives from `Rectangle`.</span></span> <span data-ttu-id="c1c2c-199">它使用 `when` 子句来确保 `ShowShapeInfo` 将已分配相等长度和宽度的 `Rectangle` 对象作为 `Square` 来处理（即使未实例化为 `Square` 对象）。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-199">It uses the `when` clause to ensure that the `ShowShapeInfo` treats a `Rectangle` object that has been assigned equal lengths and widths as a `Square` even if it has not been instantiated as a `Square` object.</span></span> <span data-ttu-id="c1c2c-200">该方法不会尝试显示关于值为 `null` 的对象或区域为零的形状的信息。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-200">The method does not attempt to display information either about an object that is `null` or a shape whose area is zero.</span></span>

[!code-csharp[when-clause#1](~/samples/snippets/csharp/language-reference/keywords/switch/when-clause.cs#1)]

<span data-ttu-id="c1c2c-201">请注意，不会执行尝试测试 `Shape` 对象是否为 `null` 的示例中的 `when` 子句。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-201">Note that the `when` clause in the example that attempts to test whether a `Shape` object is `null` does not execute.</span></span> <span data-ttu-id="c1c2c-202">测试是否为 `null` 的正确类型模式是 `case null:`。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-202">The correct type pattern to test for a `null` is `case null:`.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c1c2c-203">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c1c2c-203">C# language specification</span></span>

<span data-ttu-id="c1c2c-204">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [switch 语句](~/_csharplang/spec/statements.md#the-switch-statement)。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-204">For more information, see [The switch statement](~/_csharplang/spec/statements.md#the-switch-statement) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="c1c2c-205">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="c1c2c-205">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="c1c2c-206">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1c2c-206">See also</span></span>

- [<span data-ttu-id="c1c2c-207">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c1c2c-207">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c1c2c-208">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c1c2c-208">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c1c2c-209">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="c1c2c-209">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c1c2c-210">if-else</span><span class="sxs-lookup"><span data-stu-id="c1c2c-210">if-else</span></span>](if-else.md)
- [<span data-ttu-id="c1c2c-211">模式匹配</span><span class="sxs-lookup"><span data-stu-id="c1c2c-211">Pattern Matching</span></span>](../../pattern-matching.md)
