---
title: "for（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- for
- for_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
caps.latest.revision: 39
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
ms.openlocfilehash: d65c198b0fd763bddae4832290af038b8992eb48
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="for-c-reference"></a><span data-ttu-id="a4491-102">for（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a4491-102">for (C# Reference)</span></span>
<span data-ttu-id="a4491-103">通过使用 `for` 循环，可以重复运行一个语句或语句块，直到指定的表达式的计算结果为 `false` 为止。</span><span class="sxs-lookup"><span data-stu-id="a4491-103">By using a `for` loop, you can run a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="a4491-104">这种类型的循环可用于循环访问数组，以及事先知道循环要在其中进行循环访问的次数的其他应用程序。</span><span class="sxs-lookup"><span data-stu-id="a4491-104">This kind of loop is useful for iterating over arrays and for other applications in which you know in advance how many times you want the loop to iterate.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4491-105">示例</span><span class="sxs-lookup"><span data-stu-id="a4491-105">Example</span></span>  
 <span data-ttu-id="a4491-106">在下面的示例中，`i` 的值被写入控制台，并在循环的每次迭代过程中递增 1。</span><span class="sxs-lookup"><span data-stu-id="a4491-106">In the following example, the value of `i` is written to the console and incremented by 1 during each iteration of the loop.</span></span>  
  
 <span data-ttu-id="a4491-107">[!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4491-107">[!code-cs[csrefKeywordsIteration#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_1.cs)]</span></span>  
  
 <span data-ttu-id="a4491-108">上一示例中的 `for` 语句执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="a4491-108">The `for` statement in the previous example performs the following actions.</span></span>  
  
1.  <span data-ttu-id="a4491-109">首先，建立变量 `i` 的初始值。</span><span class="sxs-lookup"><span data-stu-id="a4491-109">First, the initial value of variable `i` is established.</span></span> <span data-ttu-id="a4491-110">无论循环重复多少次，此步骤都只发生一次。</span><span class="sxs-lookup"><span data-stu-id="a4491-110">This step happens only once, regardless of how many times the loop repeats.</span></span> <span data-ttu-id="a4491-111">可以将此初始化视为发生在循环过程之外。</span><span class="sxs-lookup"><span data-stu-id="a4491-111">You can think of this initialization as happening outside the looping process.</span></span>  
  
2.  <span data-ttu-id="a4491-112">若要计算条件 (`i <= 5`)，请将 `i` 的值与 5 相比较。</span><span class="sxs-lookup"><span data-stu-id="a4491-112">To evaluate the condition (`i <= 5`), the value of `i` is compared to 5.</span></span>  
  
    -   <span data-ttu-id="a4491-113">如果 `i` 小于或等于 5，则条件的计算结果为 `true`，并将发生以下操作。</span><span class="sxs-lookup"><span data-stu-id="a4491-113">If `i` is less than or equal to 5, the condition evaluates to `true`, and the following actions occur.</span></span>  
  
        1.  <span data-ttu-id="a4491-114">循环主体中的 `Console.WriteLine` 语句显示 `i` 的值。</span><span class="sxs-lookup"><span data-stu-id="a4491-114">The `Console.WriteLine` statement in the body of the loop displays the value of `i`.</span></span>  
  
        2.  <span data-ttu-id="a4491-115">`i` 的值增加 1。</span><span class="sxs-lookup"><span data-stu-id="a4491-115">The value of `i` is incremented by 1.</span></span>  
  
        3.  <span data-ttu-id="a4491-116">循环返回到步骤 2 的起始位置以再次计算条件。</span><span class="sxs-lookup"><span data-stu-id="a4491-116">The loop returns to the start of step 2 to evaluate the condition again.</span></span>  
  
    -   <span data-ttu-id="a4491-117">如果 `i` 大于 5，则条件的计算结果为 `false`，并退出循环。</span><span class="sxs-lookup"><span data-stu-id="a4491-117">If `i` is greater than 5, the condition evaluates to `false`, and you exit the loop.</span></span>  
  
 <span data-ttu-id="a4491-118">请注意，如果 `i` 的初始值大于 5，则循环主体一次都不会运行。</span><span class="sxs-lookup"><span data-stu-id="a4491-118">Note that, if the initial value of `i` is greater than 5, the body of the loop doesn't run even once.</span></span>  
  
 <span data-ttu-id="a4491-119">每个 `for` 语句都定义初始化表达式、条件和迭代器部分。</span><span class="sxs-lookup"><span data-stu-id="a4491-119">Every `for` statement defines initializer, condition, and iterator sections.</span></span> <span data-ttu-id="a4491-120">这些部分通常确定循环进行循环访问的次数。</span><span class="sxs-lookup"><span data-stu-id="a4491-120">These sections usually determine how many times the loop iterates.</span></span>  
  
```csharp  
for (initializer; condition; iterator)  
    body  
```  
  
 <span data-ttu-id="a4491-121">这些部分可实现以下目的。</span><span class="sxs-lookup"><span data-stu-id="a4491-121">The sections serve the following purposes.</span></span>  
  
-   <span data-ttu-id="a4491-122">初始化表达式部分设置初始条件。</span><span class="sxs-lookup"><span data-stu-id="a4491-122">The initializer section sets the initial conditions.</span></span> <span data-ttu-id="a4491-123">输入循环前，此部分中的语句仅运行一次。</span><span class="sxs-lookup"><span data-stu-id="a4491-123">The statements in this section run only once, before you enter the loop.</span></span> <span data-ttu-id="a4491-124">此部分仅可包含以下两个选项之一。</span><span class="sxs-lookup"><span data-stu-id="a4491-124">The section can contain only one of the following two options.</span></span>  
  
    -   <span data-ttu-id="a4491-125">本地循环变量的声明和初始化，如第一个示例所示 (`int i = 1`)。</span><span class="sxs-lookup"><span data-stu-id="a4491-125">The declaration and initialization of a local loop variable, as the first example shows (`int i = 1`).</span></span> <span data-ttu-id="a4491-126">变量对于循环来说是本地的，且不能从循环的外部进行访问。</span><span class="sxs-lookup"><span data-stu-id="a4491-126">The variable is local to the loop and can't be accessed from outside the loop.</span></span>  
  
    -   <span data-ttu-id="a4491-127">以下列表中显示用逗号分隔的零个或多个语句表达式。</span><span class="sxs-lookup"><span data-stu-id="a4491-127">Zero or more statement expressons from the following list, separated by commas.</span></span>  
  
        -   <span data-ttu-id="a4491-128">[赋值](../../../csharp/language-reference/operators/assignment-operator.md)语句</span><span class="sxs-lookup"><span data-stu-id="a4491-128">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
        -   <span data-ttu-id="a4491-129">方法的调用</span><span class="sxs-lookup"><span data-stu-id="a4491-129">invocation of a method</span></span>  
  
        -   <span data-ttu-id="a4491-130">为 [increment](../../../csharp/language-reference/operators/increment-operator.md) 表达式添加前缀或后缀，如 `++i` 或 `i++`</span><span class="sxs-lookup"><span data-stu-id="a4491-130">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
        -   <span data-ttu-id="a4491-131">为 [decrement](../../../csharp/language-reference/operators/decrement-operator.md) 表达式添加前缀或后缀，如 `--i` 或 `i--`</span><span class="sxs-lookup"><span data-stu-id="a4491-131">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
        -   <span data-ttu-id="a4491-132">通过使用 [new](../../../csharp/language-reference/keywords/new-operator.md) 创建对象</span><span class="sxs-lookup"><span data-stu-id="a4491-132">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
        -   <span data-ttu-id="a4491-133">[await](../../../csharp/language-reference/keywords/await.md) 表达式</span><span class="sxs-lookup"><span data-stu-id="a4491-133">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="a4491-134">条件部分包含布尔表达式，计算该表达式可确定循环应该退出还是应该再次运行。</span><span class="sxs-lookup"><span data-stu-id="a4491-134">The condition section contains a boolean expression that’s evaluated to determine whether the loop should exit or should run again.</span></span>  
  
-   <span data-ttu-id="a4491-135">迭代器部分定义循环主体的每次迭代后将执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a4491-135">The iterator section defines what happens after each iteration of the body of the loop.</span></span> <span data-ttu-id="a4491-136">迭代器部分包含用逗号分隔的零个或多个以下语句表达式：</span><span class="sxs-lookup"><span data-stu-id="a4491-136">The iterator section contains zero or more of the following statement expressions, separated by commas:</span></span>  
  
    -   <span data-ttu-id="a4491-137">[赋值](../../../csharp/language-reference/operators/assignment-operator.md)语句</span><span class="sxs-lookup"><span data-stu-id="a4491-137">[assignment](../../../csharp/language-reference/operators/assignment-operator.md) statement</span></span>  
  
    -   <span data-ttu-id="a4491-138">方法的调用</span><span class="sxs-lookup"><span data-stu-id="a4491-138">invocation of a method</span></span>  
  
    -   <span data-ttu-id="a4491-139">为 [increment](../../../csharp/language-reference/operators/increment-operator.md) 表达式添加前缀或后缀，如 `++i` 或 `i++`</span><span class="sxs-lookup"><span data-stu-id="a4491-139">prefix or postfix [increment](../../../csharp/language-reference/operators/increment-operator.md) expression, such as `++i` or `i++`</span></span>  
  
    -   <span data-ttu-id="a4491-140">为 [decrement](../../../csharp/language-reference/operators/decrement-operator.md) 表达式添加前缀或后缀，如 `--i` 或 `i--`</span><span class="sxs-lookup"><span data-stu-id="a4491-140">prefix or postfix [decrement](../../../csharp/language-reference/operators/decrement-operator.md) expression, such as `--i` or `i--`</span></span>  
  
    -   <span data-ttu-id="a4491-141">通过使用 [new](../../../csharp/language-reference/keywords/new-operator.md) 创建对象</span><span class="sxs-lookup"><span data-stu-id="a4491-141">creation of an object by using [new](../../../csharp/language-reference/keywords/new-operator.md)</span></span>  
  
    -   <span data-ttu-id="a4491-142">[await](../../../csharp/language-reference/keywords/await.md) 表达式</span><span class="sxs-lookup"><span data-stu-id="a4491-142">[await](../../../csharp/language-reference/keywords/await.md) expression</span></span>  
  
-   <span data-ttu-id="a4491-143">循环主体由一个语句、一个空语句或一个语句块（通过将零个或多个语句用大括号括起来而创建）构成。</span><span class="sxs-lookup"><span data-stu-id="a4491-143">The body of the loop consists of a statement, an empty statement, or a block of statements, which you create by enclosing zero or more statements in braces.</span></span>  
  
     <span data-ttu-id="a4491-144">可以使用关键字 [break](../../../csharp/language-reference/keywords/break.md) 中断 `for` 循环，或者可以使用关键字 [continue](../../../csharp/language-reference/keywords/continue.md) 继续执行到下一次迭代。</span><span class="sxs-lookup"><span data-stu-id="a4491-144">You can break out of a `for` loop by using the [break](../../../csharp/language-reference/keywords/break.md) keyword, or you can step to the next iteration by using the [continue](../../../csharp/language-reference/keywords/continue.md) keyword.</span></span> <span data-ttu-id="a4491-145">还可以使用 [goto](../../../csharp/language-reference/keywords/goto.md)、[return](../../../csharp/language-reference/keywords/return.md) 或 [throw](../../../csharp/language-reference/keywords/throw.md) 语句退出任何循环。</span><span class="sxs-lookup"><span data-stu-id="a4491-145">You also can exit any loop by using a [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement.</span></span>  
  
 <span data-ttu-id="a4491-146">本主题中的第一个示例显示了一种最典型的 `for` 循环，它为各部分做出了以下选择。</span><span class="sxs-lookup"><span data-stu-id="a4491-146">The first example in this topic shows the most typical kind of `for` loop, which makes the following choices for the sections.</span></span>  
  
-   <span data-ttu-id="a4491-147">初始化表达式声明并初始化本地循环变量 `i`，用于维护循环的迭代计数。</span><span class="sxs-lookup"><span data-stu-id="a4491-147">The initializer declares and initializes a local loop variable, `i`, that maintains a count of the iterations of the loop.</span></span>  
  
-   <span data-ttu-id="a4491-148">条件将针对已知的最终值 5 检查循环变量的值。</span><span class="sxs-lookup"><span data-stu-id="a4491-148">The condition checks the value of the loop variable against a known final value, 5.</span></span>  
  
-   <span data-ttu-id="a4491-149">迭代器部分使用后缀递增语句 `i++`，来计算循环的每次迭代。</span><span class="sxs-lookup"><span data-stu-id="a4491-149">The iterator section uses a postfix increment statement, `i++`, to tally each iteration of the loop.</span></span>  
  
 <span data-ttu-id="a4491-150">下面的示例阐释了几种不太常见的选择：为初始化表达式部分中的外部循环变量赋值、同时在初始化表达式部分和迭代器部分中调用 `Console.WriteLine` 方法，以及更改迭代器部分中的两个变量的值。</span><span class="sxs-lookup"><span data-stu-id="a4491-150">The following example illustrates several less common choices: assigning a value to an external loop variable in the initializer section,  invoking the `Console.WriteLine` method in both the initializer and the iterator sections, and changing the values of two variables in the iterator section.</span></span>  
  
 <span data-ttu-id="a4491-151">[!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4491-151">[!code-cs[csrefKeywordsIteration#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_2.cs)]</span></span>  
  
 <span data-ttu-id="a4491-152">定义 `for` 语句的所有表达式都是可选的。</span><span class="sxs-lookup"><span data-stu-id="a4491-152">All of the expressions that define a `for` statement are optional.</span></span> <span data-ttu-id="a4491-153">例如，以下语句创建一个无限循环。</span><span class="sxs-lookup"><span data-stu-id="a4491-153">For example, the following statement creates an infinite loop.</span></span>  
  
 <span data-ttu-id="a4491-154">[!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a4491-154">[!code-cs[csrefKeywordsIteration#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/for_3.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="a4491-155">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a4491-155">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4491-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4491-156">See Also</span></span>  
 <span data-ttu-id="a4491-157">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4491-157">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a4491-158">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4491-158">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a4491-159">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a4491-159">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a4491-160">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span><span class="sxs-lookup"><span data-stu-id="a4491-160">[foreach, in](../../../csharp/language-reference/keywords/foreach-in.md) </span></span>  
 <span data-ttu-id="a4491-161">[for 语句 (C++)](/cpp/cpp/for-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="a4491-161">[for Statement (C++)](/cpp/cpp/for-statement-cpp) </span></span>  
 [<span data-ttu-id="a4491-162">迭代语句</span><span class="sxs-lookup"><span data-stu-id="a4491-162">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

