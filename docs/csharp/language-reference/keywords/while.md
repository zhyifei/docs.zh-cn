---
title: while - C# 参考
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: ab0a8ba0b724757b4f239daf1d3319b989c4531a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "73421919"
---
# <a name="while-c-reference"></a><span data-ttu-id="75d34-102">while（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="75d34-102">while (C# Reference)</span></span>

<span data-ttu-id="75d34-103">在指定的布尔表达式的计算结果为 `true` 时，`while` 语句会执行一条语句或一个语句块。</span><span class="sxs-lookup"><span data-stu-id="75d34-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="75d34-104">由于在每次执行循环之前都会计算此表达式，所以 `while` 循环会执行零次或多次。</span><span class="sxs-lookup"><span data-stu-id="75d34-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="75d34-105">这不同于 [do](do.md) 循环，该循环执行一次或多次。</span><span class="sxs-lookup"><span data-stu-id="75d34-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="75d34-106">在 `while` 语句块中的任何点，都可使用 [break](break.md) 语句中断循环。</span><span class="sxs-lookup"><span data-stu-id="75d34-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="75d34-107">可通过使用 [continue](continue.md) 语句直接步入 `while` 表达式的计算部分。</span><span class="sxs-lookup"><span data-stu-id="75d34-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="75d34-108">如果表达式计算结果为 `true`，则继续执行循环中的第一个语句。</span><span class="sxs-lookup"><span data-stu-id="75d34-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="75d34-109">否则，将在循环后的第一个语句处继续执行。</span><span class="sxs-lookup"><span data-stu-id="75d34-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="75d34-110">还可以使用 [goto](goto.md)、[return](return.md) 或 [throw](throw.md) 语句退出 `while` 循环。</span><span class="sxs-lookup"><span data-stu-id="75d34-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="75d34-111">示例</span><span class="sxs-lookup"><span data-stu-id="75d34-111">Example</span></span>

<span data-ttu-id="75d34-112">下面的示例演示 `while` 语句的用法。</span><span class="sxs-lookup"><span data-stu-id="75d34-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="75d34-113">选择“运行”以运行示例代码  。</span><span class="sxs-lookup"><span data-stu-id="75d34-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="75d34-114">然后可以修改代码并再次运行它。</span><span class="sxs-lookup"><span data-stu-id="75d34-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="75d34-115">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="75d34-115">C# language specification</span></span>

<span data-ttu-id="75d34-116">有关详细信息，请参阅 [C# 语言规范](/dotnet/csharp/language-reference/language-specification/introduction)中的 [while 语句](~/_csharplang/spec/statements.md#the-while-statement)部分。</span><span class="sxs-lookup"><span data-stu-id="75d34-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="75d34-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="75d34-117">See also</span></span>

- [<span data-ttu-id="75d34-118">C# 参考</span><span class="sxs-lookup"><span data-stu-id="75d34-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="75d34-119">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="75d34-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="75d34-120">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="75d34-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="75d34-121">do 语句</span><span class="sxs-lookup"><span data-stu-id="75d34-121">do statement</span></span>](do.md)
