---
title: "do（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords: do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: "22"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d24078d3fb985f643fb66aa456900d03d2ff3fce
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="do-c-reference"></a><span data-ttu-id="5f33c-102">do（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5f33c-102">do (C# Reference)</span></span>
<span data-ttu-id="5f33c-103">`do` 语句重复执行一个语句或语句块，直到指定的表达式计算为 `false` 值。</span><span class="sxs-lookup"><span data-stu-id="5f33c-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="5f33c-104">循环体必须括在大括号 `{}` 内，除非它由单个语句组成。</span><span class="sxs-lookup"><span data-stu-id="5f33c-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="5f33c-105">在这种情况下，大括号是可选的。</span><span class="sxs-lookup"><span data-stu-id="5f33c-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5f33c-106">示例</span><span class="sxs-lookup"><span data-stu-id="5f33c-106">Example</span></span>  
 <span data-ttu-id="5f33c-107">在下面的示例中，只要变量 `x` 小于 5，`do-while` 循环语句就开始执行。</span><span class="sxs-lookup"><span data-stu-id="5f33c-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]  
  
 <span data-ttu-id="5f33c-108">与 [while](../../../csharp/language-reference/keywords/while.md) 语句不同的是，`do-while` 循环会在计算条件表达式之前执行一次。</span><span class="sxs-lookup"><span data-stu-id="5f33c-108">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="5f33c-109">在 `do-while` 块中的任何点，都可使用 [break](../../../csharp/language-reference/keywords/break.md) 语句跳出循环。</span><span class="sxs-lookup"><span data-stu-id="5f33c-109">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="5f33c-110">可通过使用 [continue](../../../csharp/language-reference/keywords/continue.md) 语句直接步入 `while` 表达式计算语句。</span><span class="sxs-lookup"><span data-stu-id="5f33c-110">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="5f33c-111">如果 `while` 表达式计算结果为 true，则继续执行循环中的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="5f33c-111">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="5f33c-112">如果表达式的计算结果为 false，则继续执行 `do-while` 循环后的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="5f33c-112">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="5f33c-113">`do-while` 循环还可以通过 [goto](../../../csharp/language-reference/keywords/goto.md)、[return](../../../csharp/language-reference/keywords/return.md) 或 [throw](../../../csharp/language-reference/keywords/throw.md) 语句退出。</span><span class="sxs-lookup"><span data-stu-id="5f33c-113">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="5f33c-114">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="5f33c-114">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f33c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f33c-115">See Also</span></span>  
 [<span data-ttu-id="5f33c-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5f33c-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="5f33c-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5f33c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="5f33c-118">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="5f33c-118">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="5f33c-119">do-while 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="5f33c-119">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="5f33c-120">迭代语句</span><span class="sxs-lookup"><span data-stu-id="5f33c-120">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
