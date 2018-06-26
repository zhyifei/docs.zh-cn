---
title: do（C# 参考）
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: b918b378623a239803fb4e0a65fcf82fd677b21f
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34566080"
---
# <a name="do-c-reference"></a><span data-ttu-id="81ddb-102">do（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="81ddb-102">do (C# Reference)</span></span>

<span data-ttu-id="81ddb-103">在指定的布尔表达式的计算结果为 `true` 时，`do` 语句会执行一条语句或一个语句块。</span><span class="sxs-lookup"><span data-stu-id="81ddb-103">The `do` statement executes a statement or a block of statements while a specified boolean expression evaluates to `true`.</span></span> <span data-ttu-id="81ddb-104">由于在每次执行循环之后都会计算此表达式，所以 `do-while` 循环会执行一次或多次。</span><span class="sxs-lookup"><span data-stu-id="81ddb-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="81ddb-105">这不同于 [while](while.md) 循环（该循环执行零次或多次）。</span><span class="sxs-lookup"><span data-stu-id="81ddb-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="81ddb-106">在 `do` 语句块中的任何点，都可使用 [break](break.md) 语句中断循环。</span><span class="sxs-lookup"><span data-stu-id="81ddb-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="81ddb-107">可通过使用 [continue](continue.md) 语句直接步入 `while` 表达式的计算部分。</span><span class="sxs-lookup"><span data-stu-id="81ddb-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="81ddb-108">如果表达式计算结果为 `true`，则继续执行循环中的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="81ddb-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="81ddb-109">否则，将在循环后的第一个语句处继续执行。</span><span class="sxs-lookup"><span data-stu-id="81ddb-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="81ddb-110">还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `do-while` 循环。</span><span class="sxs-lookup"><span data-stu-id="81ddb-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="81ddb-111">示例</span><span class="sxs-lookup"><span data-stu-id="81ddb-111">Example</span></span>

<span data-ttu-id="81ddb-112">下面的示例演示 `do` 语句的用法。</span><span class="sxs-lookup"><span data-stu-id="81ddb-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="81ddb-113">选择“运行”以运行示例代码。</span><span class="sxs-lookup"><span data-stu-id="81ddb-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="81ddb-114">然后可以修改代码并再次运行它。</span><span class="sxs-lookup"><span data-stu-id="81ddb-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="81ddb-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="81ddb-115">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="81ddb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="81ddb-116">See also</span></span>

 [<span data-ttu-id="81ddb-117">C# 参考</span><span class="sxs-lookup"><span data-stu-id="81ddb-117">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="81ddb-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="81ddb-118">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="81ddb-119">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="81ddb-119">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="81ddb-120">do-while 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="81ddb-120">do-while Statement (C++)</span></span>](/cpp/cpp/do-while-statement-cpp)  
 [<span data-ttu-id="81ddb-121">迭代语句</span><span class="sxs-lookup"><span data-stu-id="81ddb-121">Iteration Statements</span></span>](iteration-statements.md)  
 [<span data-ttu-id="81ddb-122">while 语句</span><span class="sxs-lookup"><span data-stu-id="81ddb-122">while statement</span></span>](while.md)  
