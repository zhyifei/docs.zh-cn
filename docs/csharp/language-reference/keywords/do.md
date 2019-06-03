---
title: do - C# 参考
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- do_CSharpKeyword
- do
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
ms.openlocfilehash: 5566965e77feb9d46584146829284e9e0be71539
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422040"
---
# <a name="do-c-reference"></a><span data-ttu-id="2de7a-102">do（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="2de7a-102">do (C# Reference)</span></span>

<span data-ttu-id="2de7a-103">在指定的布尔表达式的计算结果为 `true` 时，`do` 语句会执行一条语句或一个语句块。</span><span class="sxs-lookup"><span data-stu-id="2de7a-103">The `do` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="2de7a-104">由于在每次执行循环之后都会计算此表达式，所以 `do-while` 循环会执行一次或多次。</span><span class="sxs-lookup"><span data-stu-id="2de7a-104">Because that expression is evaluated after each execution of the loop, a `do-while` loop executes one or more times.</span></span> <span data-ttu-id="2de7a-105">这不同于 [while](while.md) 循环（该循环执行零次或多次）。</span><span class="sxs-lookup"><span data-stu-id="2de7a-105">This differs from the [while](while.md) loop, which executes zero or more times.</span></span>

<span data-ttu-id="2de7a-106">在 `do` 语句块中的任何点，都可使用 [break](break.md) 语句中断循环。</span><span class="sxs-lookup"><span data-stu-id="2de7a-106">At any point within the `do` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="2de7a-107">可通过使用 [continue](continue.md) 语句直接步入 `while` 表达式的计算部分。</span><span class="sxs-lookup"><span data-stu-id="2de7a-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="2de7a-108">如果表达式计算结果为 `true`，则继续执行循环中的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="2de7a-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="2de7a-109">否则，将在循环后的第一个语句处继续执行。</span><span class="sxs-lookup"><span data-stu-id="2de7a-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="2de7a-110">还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `do-while` 循环。</span><span class="sxs-lookup"><span data-stu-id="2de7a-110">You also can exit a `do-while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="2de7a-111">示例</span><span class="sxs-lookup"><span data-stu-id="2de7a-111">Example</span></span>

<span data-ttu-id="2de7a-112">下面的示例演示 `do` 语句的用法。</span><span class="sxs-lookup"><span data-stu-id="2de7a-112">The following example shows the usage of the `do` statement.</span></span> <span data-ttu-id="2de7a-113">选择“运行”以运行示例代码  。</span><span class="sxs-lookup"><span data-stu-id="2de7a-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="2de7a-114">然后可以修改代码并再次运行它。</span><span class="sxs-lookup"><span data-stu-id="2de7a-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[do loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="2de7a-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="2de7a-115">C# language specification</span></span>

<span data-ttu-id="2de7a-116">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [do 语句](~/_csharplang/spec/statements.md#the-do-statement)部分。</span><span class="sxs-lookup"><span data-stu-id="2de7a-116">For more information, see [The do statement](~/_csharplang/spec/statements.md#the-do-statement) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2de7a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2de7a-117">See also</span></span>

- [<span data-ttu-id="2de7a-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="2de7a-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2de7a-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2de7a-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2de7a-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="2de7a-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="2de7a-121">while 语句</span><span class="sxs-lookup"><span data-stu-id="2de7a-121">while statement</span></span>](while.md)
