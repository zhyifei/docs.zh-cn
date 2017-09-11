---
title: "if-else（C# 参考）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- if_CSharpKeyword
- else
- else_CSharpKeyword
- if
dev_langs:
- CSharp
helpviewer_keywords:
- else keyword [C#]
- if keyword [C#]
ms.assetid: d9a1d562-8cf5-4bd4-9ba7-8ad970cd25b2
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 694761a9b03fadf2dff97e61e37c0af52658f9e4
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="if-else-c-reference"></a><span data-ttu-id="a8b28-102">if-else（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="a8b28-102">if-else (C# Reference)</span></span>
<span data-ttu-id="a8b28-103">`if` 语句基于 `Boolean` 表达式的值来识别运行哪个语句。</span><span class="sxs-lookup"><span data-stu-id="a8b28-103">An `if` statement identifies which statement to run based on the value of a `Boolean` expression.</span></span> <span data-ttu-id="a8b28-104">在下面的示例中， `Boolean` 变量 `result` 已被设置为 `true` ，然后被签入到了 `if` 语句。</span><span class="sxs-lookup"><span data-stu-id="a8b28-104">In the following example, the `Boolean` variable `result` is set to `true` and then checked in the `if` statement.</span></span> <span data-ttu-id="a8b28-105">输出为 `The condition is true`。</span><span class="sxs-lookup"><span data-stu-id="a8b28-105">The output is `The condition is true`.</span></span>  
  
 <span data-ttu-id="a8b28-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8b28-106">[!code-cs[csrefKeywordsSelection#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_1.cs)]</span></span>  
  
 <span data-ttu-id="a8b28-107">你可以通过将本主题中的示例放入控制台应用的 `Main` 方法中来运行它们。</span><span class="sxs-lookup"><span data-stu-id="a8b28-107">You can run the examples in this topic by placing them in the `Main` method of a console app.</span></span>  
  
 <span data-ttu-id="a8b28-108">C# 中的 `if` 语句可以采用两种形式，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a8b28-108">An `if` statement in C# can take two forms, as the following example shows.</span></span>  
  
```csharp  
// if-else statement  
if (condition)  
{  
    then-statement;  
}  
else  
{  
    else-statement;  
}  
// Next statement in the program.  
  
// if statement without an else  
if (condition)  
{  
    then-statement;  
}  
// Next statement in the program.  
```  
  
 <span data-ttu-id="a8b28-109">在 `if-else` 语句中，如果 `condition` 计算结果为 true，则 `then-statement` 将运行。</span><span class="sxs-lookup"><span data-stu-id="a8b28-109">In an `if-else` statement, if `condition` evaluates to true, the `then-statement` runs.</span></span> <span data-ttu-id="a8b28-110">如果 `condition` 为 false，则 `else-statement` 将运行。</span><span class="sxs-lookup"><span data-stu-id="a8b28-110">If `condition` is false, the `else-statement` runs.</span></span> <span data-ttu-id="a8b28-111">由于 `condition` 不能同时为 true 和 false，因此， `then-statement` 语句的 `else-statement` 和 `if-else` 永远不能同时运行。</span><span class="sxs-lookup"><span data-stu-id="a8b28-111">Because `condition` can’t be simultaneously true and false, the `then-statement` and the `else-statement` of an `if-else` statement can never both run.</span></span> <span data-ttu-id="a8b28-112">`then-statement` 或 `else-statement` 运行后，控件将转移到 `if` 语句之后的下一个语句。</span><span class="sxs-lookup"><span data-stu-id="a8b28-112">After the `then-statement` or the `else-statement` runs, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="a8b28-113">在不包括 `if` 语句的 `else` 语句中，如果 `condition` 为 true，则 `then-statement` 将运行。</span><span class="sxs-lookup"><span data-stu-id="a8b28-113">In an `if` statement that doesn’t include an `else` statement, if `condition` is true, the `then-statement` runs.</span></span> <span data-ttu-id="a8b28-114">如果 `condition` 为 false，则控件将转移到 `if` 语句之后的下一个语句。</span><span class="sxs-lookup"><span data-stu-id="a8b28-114">If `condition` is false, control is transferred to the next statement after the `if` statement.</span></span>  
  
 <span data-ttu-id="a8b28-115">`then-statement` 和 `else-statement` 都可由单个语句或包含在括号中 (`{}`) 的多个语句组成。</span><span class="sxs-lookup"><span data-stu-id="a8b28-115">Both the `then-statement` and the `else-statement` can consist of a single statement or multiple statements that are enclosed in braces (`{}`).</span></span> <span data-ttu-id="a8b28-116">对于单个语句，括号是可选的，但建议选择。</span><span class="sxs-lookup"><span data-stu-id="a8b28-116">For a single statement, the braces are optional but recommended.</span></span>  
  
 <span data-ttu-id="a8b28-117">`then-statement` 和 `else-statement` 中的语句可为任何类型，包括嵌套在原始 `if` 语句中的另一个 `if` 语句。</span><span class="sxs-lookup"><span data-stu-id="a8b28-117">The statement or statements in the `then-statement` and the `else-statement` can be of any kind, including another `if` statement nested inside the original `if` statement.</span></span> <span data-ttu-id="a8b28-118">在嵌套的 `if` 语句中，每个 `else` 子句都属于上一个无相应 `if` 的 `else`。</span><span class="sxs-lookup"><span data-stu-id="a8b28-118">In nested `if` statements, each `else` clause belongs to the last `if` that doesn’t have a corresponding `else`.</span></span> <span data-ttu-id="a8b28-119">在下面的示例中，如果 `Result1` 和 `m > 10` 计算结果都为 true，则将显示 `n > 20` 。</span><span class="sxs-lookup"><span data-stu-id="a8b28-119">In the following example, `Result1` appears if both `m > 10` and `n > 20` evaluate to true.</span></span> <span data-ttu-id="a8b28-120">如果 `m > 10` 为 true 但 `n > 20` 为 false，则将显示 `Result2` 。</span><span class="sxs-lookup"><span data-stu-id="a8b28-120">If `m > 10` is true but `n > 20` is false, `Result2` appears.</span></span>  
  
 <span data-ttu-id="a8b28-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8b28-121">[!code-cs[csrefKeywordsSelection#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_2.cs)]</span></span>  
  
 <span data-ttu-id="a8b28-122">相反，如果你希望在 `Result2` 为 false 的时候显示 `(m > 10)` ，则可以通过使用括号来指定此关联，以建立嵌套的 `if` 语句的开头和结尾，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a8b28-122">If, instead, you want `Result2` to appear when `(m > 10)` is false, you can specify that association by using braces to establish the start and end of the nested `if` statement, as the following example shows.</span></span>  
  
 <span data-ttu-id="a8b28-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8b28-123">[!code-cs[csrefKeywordsSelection#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_3.cs)]</span></span>  
  
 <span data-ttu-id="a8b28-124">如果条件 `(m > 10)` 的计算结果为 false，则显示 `Result2`。</span><span class="sxs-lookup"><span data-stu-id="a8b28-124">`Result2` appears if the condition `(m > 10)` evaluates to false.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8b28-125">示例</span><span class="sxs-lookup"><span data-stu-id="a8b28-125">Example</span></span>  
 <span data-ttu-id="a8b28-126">在下例中，当通过键盘输入字符时，该程序将使用嵌套的 `if` 语句来确定输入的字符是否为字母字符。</span><span class="sxs-lookup"><span data-stu-id="a8b28-126">In the following example, you enter a character from the keyboard, and the program uses a nested `if` statement to determine whether the input character is an alphabetic character.</span></span> <span data-ttu-id="a8b28-127">如果输入的字符是字母字符，则程序将检查输入的字符是大写还是小写。</span><span class="sxs-lookup"><span data-stu-id="a8b28-127">If the input character is an alphabetic character, the program checks whether the input character is lowercase or uppercase.</span></span> <span data-ttu-id="a8b28-128">每种情况都会显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="a8b28-128">A message appears for each case.</span></span>  
  
 <span data-ttu-id="a8b28-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8b28-129">[!code-cs[csrefKeywordsSelection#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_4.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8b28-130">示例</span><span class="sxs-lookup"><span data-stu-id="a8b28-130">Example</span></span>  
 <span data-ttu-id="a8b28-131">你也可以将 `if` 语句嵌套到 else 块中，如以下部分代码所示。</span><span class="sxs-lookup"><span data-stu-id="a8b28-131">You also can nest an `if` statement inside an else block, as the following partial code shows.</span></span> <span data-ttu-id="a8b28-132">示例将 `if` 语句嵌套在两个 else 块和一个 then 块中。</span><span class="sxs-lookup"><span data-stu-id="a8b28-132">The example nests `if` statements inside two else blocks and one then block.</span></span> <span data-ttu-id="a8b28-133">注释指定每个块中哪些条件为 true 哪些条件为 false。</span><span class="sxs-lookup"><span data-stu-id="a8b28-133">The comments specify which conditions are true or false in each block.</span></span>  
  
 <span data-ttu-id="a8b28-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8b28-134">[!code-cs[csrefKeywordsSelection#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_5.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8b28-135">示例</span><span class="sxs-lookup"><span data-stu-id="a8b28-135">Example</span></span>  
 <span data-ttu-id="a8b28-136">下面的示例确定了输入的字符是一个小写字母，还是大写字母，还是一个数字。</span><span class="sxs-lookup"><span data-stu-id="a8b28-136">The following example determines whether an input character is a lowercase letter, an uppercase letter, or a number.</span></span> <span data-ttu-id="a8b28-137">如果所有三个条件都为 false，该字符不是字母数字字符。</span><span class="sxs-lookup"><span data-stu-id="a8b28-137">If all three conditions are false, the character isn’t an alphanumeric character.</span></span> <span data-ttu-id="a8b28-138">此示例显示了每种情况的消息内容。</span><span class="sxs-lookup"><span data-stu-id="a8b28-138">The example displays a message for each case.</span></span>  
  
 <span data-ttu-id="a8b28-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span><span class="sxs-lookup"><span data-stu-id="a8b28-139">[!code-cs[csrefKeywordsSelection#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/if-else_6.cs)]</span></span>  
  
 <span data-ttu-id="a8b28-140">正如 else 块或 then 块中的语句可以是任何有效的语句一样，你可以将任何有效的布尔表达式用于此条件。</span><span class="sxs-lookup"><span data-stu-id="a8b28-140">Just as a statement in the else block or the then block can be any valid statement, you can use any valid Boolean expression for the condition.</span></span> <span data-ttu-id="a8b28-141">可以使用诸如 [&&](../../../csharp/language-reference/operators/conditional-and-operator.md)、[&](../../../csharp/language-reference/operators/and-operator.md)、[&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md)、[&#124;](../../../csharp/language-reference/operators/or-operator.md) 和 [!](../../../csharp/language-reference/operators/logical-negation-operator.md) 之类</span><span class="sxs-lookup"><span data-stu-id="a8b28-141">You can use logical operators such as [&&](../../../csharp/language-reference/operators/conditional-and-operator.md), [&](../../../csharp/language-reference/operators/and-operator.md), [&#124;&#124;](../../../csharp/language-reference/operators/conditional-or-operator.md), [&#124;](../../../csharp/language-reference/operators/or-operator.md) and [!](../../../csharp/language-reference/operators/logical-negation-operator.md)</span></span> <span data-ttu-id="a8b28-142">的逻辑运算符来创建符合条件。</span><span class="sxs-lookup"><span data-stu-id="a8b28-142">to make compound conditions.</span></span> <span data-ttu-id="a8b28-143">下面的代码演示了示例。</span><span class="sxs-lookup"><span data-stu-id="a8b28-143">The following code shows examples.</span></span>  
  
```csharp  
// NOT  
bool result = true;  
if (!result)  
{  
    Console.WriteLine("The condition is true (result is false).");  
}  
else  
{  
    Console.WriteLine("The condition is false (result is true).");  
}  
  
// Short-circuit AND  
int m = 9;  
int n = 7;  
int p = 5;  
if (m >= n && m >= p)  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// AND and NOT  
if (m >= n && !(p > m))  
{  
    Console.WriteLine("Nothing is larger than m.");  
}  
  
// Short-circuit OR  
if (m > n || m > p)  
{  
    Console.WriteLine("m isn't the smallest.");  
}  
  
// NOT and OR  
m = 4;  
if (!(m >= n || m >= p))  
{  
    Console.WriteLine("Now m is the smallest.");  
}  
// Output:  
// The condition is false (result is true).  
// Nothing is larger than m.  
// Nothing is larger than m.  
// m isn't the smallest.  
// Now m is the smallest.  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="a8b28-144">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="a8b28-144">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a8b28-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="a8b28-145">See Also</span></span>  
 <span data-ttu-id="a8b28-146">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8b28-146">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="a8b28-147">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8b28-147">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="a8b28-148">[C# 关键字](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="a8b28-148">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="a8b28-149">[?: 运算符](../../../csharp/language-reference/operators/conditional-operator.md) </span><span class="sxs-lookup"><span data-stu-id="a8b28-149">[?: Operator](../../../csharp/language-reference/operators/conditional-operator.md) </span></span>  
 <span data-ttu-id="a8b28-150">[if-else 语句 (C++)](/cpp/cpp/if-else-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="a8b28-150">[if-else Statement (C++)](/cpp/cpp/if-else-statement-cpp) </span></span>  
 [<span data-ttu-id="a8b28-151">switch</span><span class="sxs-lookup"><span data-stu-id="a8b28-151">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)

