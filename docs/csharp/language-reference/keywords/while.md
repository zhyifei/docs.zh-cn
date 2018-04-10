---
title: while（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 22
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a><span data-ttu-id="04bcf-102">while（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="04bcf-102">while (C# Reference)</span></span>
<span data-ttu-id="04bcf-103">`while` 语句执行一条语句或一个语句块，直到指定的表达式的计算结果为 `false` 为止。</span><span class="sxs-lookup"><span data-stu-id="04bcf-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04bcf-104">示例</span><span class="sxs-lookup"><span data-stu-id="04bcf-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="04bcf-105">示例</span><span class="sxs-lookup"><span data-stu-id="04bcf-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="04bcf-106">示例</span><span class="sxs-lookup"><span data-stu-id="04bcf-106">Example</span></span>  
 <span data-ttu-id="04bcf-107">因为 `while` 表达式的测试在每次执行循环之前开始，所以 `while` 循环执行零次或多次。</span><span class="sxs-lookup"><span data-stu-id="04bcf-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="04bcf-108">这不同于 [do](../../../csharp/language-reference/keywords/do.md) 循环，该循环执行一次或多次。</span><span class="sxs-lookup"><span data-stu-id="04bcf-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="04bcf-109">[break](../../../csharp/language-reference/keywords/break.md)、[goto](../../../csharp/language-reference/keywords/goto.md)、[return](../../../csharp/language-reference/keywords/return.md) 或 [throw](../../../csharp/language-reference/keywords/throw.md) 语句将控制转移到循环外时，`while` 循环可能终止。</span><span class="sxs-lookup"><span data-stu-id="04bcf-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="04bcf-110">若要将控制传递到下一个迭代，而不退出循环，则使用 [continue](../../../csharp/language-reference/keywords/continue.md) 语句。</span><span class="sxs-lookup"><span data-stu-id="04bcf-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="04bcf-111">注意前面三个示例的输出差异，具体取决于 `int n` 递增的位置。</span><span class="sxs-lookup"><span data-stu-id="04bcf-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="04bcf-112">在以下示例中，未生成任何输出。</span><span class="sxs-lookup"><span data-stu-id="04bcf-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="04bcf-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="04bcf-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="04bcf-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04bcf-114">See Also</span></span>  
 [<span data-ttu-id="04bcf-115">C# 参考</span><span class="sxs-lookup"><span data-stu-id="04bcf-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="04bcf-116">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="04bcf-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04bcf-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="04bcf-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="04bcf-118">While 语句 (C++)</span><span class="sxs-lookup"><span data-stu-id="04bcf-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="04bcf-119">迭代语句</span><span class="sxs-lookup"><span data-stu-id="04bcf-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
